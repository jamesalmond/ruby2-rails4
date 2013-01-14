!SLIDE
# Strong Parameters

!SLIDE

# Rails 3.x

    @@@ ruby
    class Person < ActiveRecord::Base
      attr_accessible :name, :name
    end

    # controller
    def create
      User.create!(params[:user])
    end

!SLIDE small

# Rails 4.0

    @@@ ruby
    class Person < ActiveRecord::Base
      include ActiveModel::ForbiddenAttributesProtection
    end

    # controller
    def create
      User.create!(person_params)
    end

    private
      def person_params
        params.require(:person).permit(:name, :age)
      end
