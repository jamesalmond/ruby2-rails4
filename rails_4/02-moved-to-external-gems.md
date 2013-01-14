!SLIDE
# What's been removed?

!SLIDE bullets incremental

# Moved to a gem

* Active Record session store
* Observers
* Active Resource
* Action pack action caching
* Action pack page caching
* Sprockets


!SLIDE bullets incremental small

# Hash based finders

    @@@ ruby
    Post.find( :all,
      conditions: { published_on: 2.weeks.ago }
    )

* deprecated in 4, removed in 4.1

!SLIDE

# ActiveRecord assignment protection
## (more on this later)
    @@@ ruby
    attr_accessible :field
    attr_protected  :field

!SLIDE

# <del>vendor/plugins</del>
