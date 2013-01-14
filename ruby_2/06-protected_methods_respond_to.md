!SLIDE
# Changes to #respond_to?


!SLIDE execute

    @@@ ruby
    class Heart
      def public_method; end

      protected
      def protected_method; end

      private
      def private_method; end
    end

    Heart.new.public_method

!SLIDE execute

    @@@ ruby
    class Heart
      def public_method; end

      protected
      def protected_method; end

      private
      def private_method; end
    end

    Heart.new.protected_method

!SLIDE execute

    @@@ ruby
    class Heart
      def public_method; end

      protected
      def protected_method; end

      private
      def private_method; end
    end

    Heart.new.private_method

!SLIDE execute
    @@@ ruby
    Heart.new.respond_to? :public_method

    # => 1.9: true

!SLIDE execute
    @@@ ruby
    Heart.new.respond_to? :private_method

    # => 1.9: false

!SLIDE execute
    @@@ ruby
    Heart.new.respond_to? :protected_method

    # => 1.9: true
