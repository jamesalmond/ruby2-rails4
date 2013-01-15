!SLIDE

# Keyword arguments

.notes similar to hash based params

!SLIDE
# Example:
## [links]
.notes we want to take a piece of text and wrap it in some characters

!SLIDE execute

# Ruby 1.9

    @@@ ruby
    def wrap(text, opts={})
      "#{opts[:before]}#{text}#{opts[:after]}"
    end

    wrap("link", before: "[", after: "]")


!SLIDE execute
# Ruby 1.9
    @@@ ruby
    wrap("link")

.notes what if we want some defaults, or want to leave one out?

!SLIDE execute
# Ruby 1.9
    @@@ ruby
    wrap("link", before: "[!")

!SLIDE execute
# Ruby 1.9
    @@@ ruby
    wrap("link", after: "!]")

!SLIDE execute

# Ruby 1.9

    @@@ ruby
    def wrap(text, opts={})
      before = opts.fetch(:before, "[")
      after = opts.fetch(:after, "]")
      "#{before}#{text}#{after}"
    end

    wrap("link")

!SLIDE execute

# Ruby 2.0

    @@@ ruby
    def wrap(text, before: "[", after: "]")
      "#{before}#{text}#{after}"
    end

    wrap("link", before: '[', after: ']')

.notes can use them by name in the method rather than inspecting a hash and set defaults

!SLIDE execute

# Ruby 2.0

    @@@ ruby
    def wrap(text, before: "[", after: "]")
      "#{before}#{text}#{after}"
    end

    wrap("link", before: "[!")

!SLIDE execute

# Ruby 2.0

    @@@ ruby
    def wrap(text, before: "[", after: "]")
      "#{before}#{text}#{after}"
    end

    wrap("link", after: ")", before: "(")

.notes ordering not important

!SLIDE execute

# Ruby 2.0

    @@@ ruby
    def wrap(text, before: "[", after: "]")
      "#{before}#{text}#{after}"
    end

    wrap("link")
