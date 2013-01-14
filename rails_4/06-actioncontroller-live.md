!SLIDE
# ActionController::Live

!SLIDE small

    @@@ ruby
    class MyController < ActionController::Base
      include ActionController::Live

      def stream
        100.times {
          response.stream.write "hello world\n"
          sleep 1
        }
        response.stream.close
      end
    end
