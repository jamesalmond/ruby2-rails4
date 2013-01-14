!SLIDE
# Module#prepend

!SLIDE execute

    @@@ ruby
    module LoudHailer
      def shout(message)
        "#{message}!"
      end
    end

    class Hello
      include LoudHailer
    end

    Hello.new.shout("We love to ruby")

!SLIDE execute

    @@@ ruby
    module LoudHailer
      def shout(message)
        "#{message}!"
      end
    end

    class Bonjour
      include LoudHailer

      def shout(message)
        "I SAID: #{message}"
      end
    end

    Bonjour.new.shout("We love to ruby")

!SLIDE execute

    @@@ ruby
    module LoudHailer
      def shout(message)
        "#{message}!"
      end
    end

    class Hallo
      prepend LoudHailer

      def shout(message)
        "I SAID: #{message}"
      end
    end

    Hallo.new.shout("We love to ruby")

!SLIDE execute

    @@@ ruby

    module Microphone
      def shout(message)
        "Testing 1, 2: #{message}"
      end
    end

    class Yo
      include LoudHailer
      include Microphone
    end

    Yo.new.shout("We love to ruby")

!SLIDE execute

    @@@ ruby
    class Howdy
      prepend LoudHailer
      include Microphone
    end

    Howdy.new.shout("We love to ruby")
