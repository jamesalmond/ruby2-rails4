!SLIDE
# Cache digests

!SLIDE small
# Rails 3.x
    @@@ ruby
    # app/views/projects/show.html.erb
    <% cache project do %>
      <h1>All documents</h1>
      <%= render project.documents %>
      <h1>All todolists</h1>
      <%= render project.todolists %>
    <% end %>

!SLIDE small
# Rails 3.x
    @@@ ruby
    # app/views/documents/_document.html.erb
    <% cache document do %>
      My document: <%= document.name %>
      <%= render document.comments %>
    <% end %>

    # app/views/todolists/_todolist.html.erb
    <% cache todolist do %>
      My todolist: <%= todolist.name %>
    <% end %>

!SLIDE small
# Rails 3.x
    @@@ ruby
    # app/views/projects/show.html.erb
    <% cache [ "v1", project ] do %>
      <h1>All documents</h1>
      <%= render project.documents %>
      <h1>All todolists</h1>
      <%= render project.todolists %>
    <% end %>

!SLIDE small
# Rails 3.x
    @@@ ruby
    # app/views/documents/_document.html.erb
    <% cache [ "v1", document ] do %>
      My document: <%= document.name %>
      <%= render document.comments %>
    <% end %>

    # app/views/todolists/_todolist.html.erb
    <% cache [ "v1", todolist ] do %>
      My todolist: <%= todolist.name %>
    <% end %>

!SLIDE small
# Rails 4.0
    @@@ ruby
    # app/views/projects/show.html.erb
    <% cache project do %>
      <h1>All documents</h1>
      <%= render project.documents %>
      <h1>All todolists</h1>
      <%= render project.todolists %>
    <% end %>

!SLIDE small
# Rails 4.0
    @@@ ruby
    # app/views/documents/_document.html.erb
    <% cache document do %>
      My document: <%= document.name %>
      <%= render document.comments %>
    <% end %>

    # app/views/todolists/_todolist.html.erb
    <% cache todolist do %>
      My todolist: <%= todolist.name %>
    <% end %>
