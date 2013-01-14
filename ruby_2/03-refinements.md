!SLIDE

# Refinements

.notes introduced to help reduce the effect of monkey patching

!SLIDE execute

    @@@ ruby
    # require 'megaphone'
    class Megaphone
      def shout(message)
        "#{message}!"
      end
    end 

    Megaphone.new.shout("Ruby is awesome")

.notes external library called megaphone

!SLIDE execute

    @@@ ruby
    # require 'megaphone'
    class Megaphone
      def shout(message)
        "#{message}!"
      end
    end 

    # in our code
    Megaphone.class_eval do
      def shout(message)
        "OMG, #{message}!!!!!1!!"
      end
    end 

    Megaphone.new.shout("Ruby is awesome")

.notes This change is available throughout our application, AND within the library!

!SLIDE execute

    @@@ ruby
    module MyMegaphone
      refine Megaphone do
        def shout(message)
          "OMG, #{message}!!!!!1!!"
        end
      end
    end

!SLIDE execute

    @@@ ruby
    module MyApp
      using MyMegaphone
      Megaphone.new.shout("Ruby is awesome")
    end
    #  => OMG, Ruby is awesome!!!!!1!!

!SLIDE execute

    @@@ ruby
    module MyApp
      using MyMegaphone
      Megaphone.new.shout("Ruby is awesome")
    end
    #  => OMG, Ruby is awesome!!!!!1!!

    Megaphone.new.shout("Ruby is awesome") 
    #  => Ruby is awesome!

!SLIDE
# But...
.notes that's not quite how it's going to work

!SLIDE execute

    @@@ ruby

    module MyMegaphone
      refine Megaphone do
        def shout(message)
          "OMG, #{message}!!!!!1!!"
        end
      end
    end

    Megaphone.new.shout("Ruby is awesome")
    #  => Ruby is awesome!
    using MyMegaphone
    Megaphone.new.shout("Ruby is awesome") 
    #  => OMG, Ruby is awesome!!!!!1!!

.notes Bah, this feature is now scoped to files and not classes

