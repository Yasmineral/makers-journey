# Frontend, single page app guidance

* How will you serve your app? Maybe a very simple node library like :pill: [http-server](../pills/http_server.md)? (This is exempt from the "no frameworks, no libraries" rule.)

* How will you write and run unit tests? Have a look at :pill: [writing tests without a testing library](../pills/writing_tests_without_a_testing_library.md).

* Maybe you won't write any feature tests.  If you do, how will you do it? Maybe you could write tests as functions that use DOM methods like `click` to click on things, and include your test file into your `index.html` when you want to run your tests?

* How will you intercept form submissions so they don't reload the page? `form submit event` and `preventDefault` may prove useful.

* How will you intercept URL changes so that they don't reload the page? Have a look at :pill: [frontend, single page app](../pills/frontend_single_page_app.md).

* How will you implement the domain model? Maybe the [constructor and prototype pattern](https://github.com/makersacademy/skills-workshops/tree/master/week-5/encapsulation_with_constructor_and_prototype_pattern)?

* How will you construct your HTML content? You could write a view module.  Maybe it will concatenate strings? Maybe it will use a tiny tiny templating framework that you write.

* How will you map URLs to resources? How will you render HTML to the page? How will you let your HTML interface interact with your models in a clean way? Maybe a controller or two?

* How will you make requests to external APIs? Maybe Ajax with raw XMLHttpRequest objects?


![Tracking pixel](https://githubanalytics.herokuapp.com/course/further_javascript/frontend_single_page_app_guidance.md)
