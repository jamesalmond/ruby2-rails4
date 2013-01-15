!SLIDE
# Routing Concerns

!SLIDE
# Rails 3.x

    @@@ ruby
    Application.routes.draw do
      resources :articles do
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

!SLIDE smaller
# Rails 4.0

    @@@ ruby
    Application.routes.draw do
      concern :commentable do
        resources :comments
      end

      concern :rateable do
        resources :ratings
      end

      resources :articles, concerns: [:commentable, :rateable]
      resources :jobs, concerns: [:commentable, :rateable]
      resources :profiles, concerns: [:commentable]
    end
