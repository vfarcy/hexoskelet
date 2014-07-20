title: 'Do you speak UML ?'
date: 2014-07-20 09:59:18
tags:
---

{% uml %}
@found "Browser", ->
  @alt {
    "[200]": -> @message "GET href resources", "HTTP Server"
    "[301]": -> @ref "GET the moved page"
    "[404]": -> @ref "show NOT FOUND"
  }
@find(".ref").css(width:256, "padding-bottom":4)
  .find(".tag").css float:"left"
get_the_moved_page.css "background-color":"#80c080"
show_not_found.css "background-color":"#f0b0b0"
{% enduml %}

