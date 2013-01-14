!SLIDE
# Routing Concerns

!SLIDE
# Rails 3.x

    @@@ ruby
    Application.routes.draw do
      resources :arcticles do
        resources :comments
        resources :ratings
      end
      resources :jobs do
        resources :comments
        resources :ratings
      end
      resources :profiles do
        resources :comments
      end
    end

!SLIDE small
# Rails 4.0

    @@@ ruby
    Application.routes.draw do
      concern :commentable do
        resources :comments
      end

      concern :rateable do
        resources :ratings
      end

      resources :arcticles,
        concerns: [:commentable, :rateable]
      resources :jobs,
        concerns: [:commentable, :rateable]
      resources :profiles,
        concerns: [:commentable]
    end
