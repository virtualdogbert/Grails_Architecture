# Grails_Architecture

High level breakdown of the parts of Grails:
* UrlMappings: Point incoming urls, from views, js or a seperate frontend, to controllers.
* Controllers: used for routing, rendering(views/strings), and calling services, maybe some light parameter checking*. Your business logic shouldn't be here.
* Services: where you business logic should be, and where you should manipulate domain objects.
* Views: rendered from controllers, to return html, json etc.
* Domains: These are your representation of your data source, often SQL tables, or NoSql objects. These can have constraint logic in them, but don't go overboard with, adding additional functions and logic, that should be in your services.
* Command objects: this is where you can do extensive parameter checking. They are like domain objects, but without the persistence. Command objects, don't currently have a convention other than they  implement the Validateable trait, and can be used to bind incoming params in controllers. I've actually written a plugin, that gives them more of a convention, which I'm just waiting to be included into the Grails plugin repo. The plugin isn't perfect yet(1.0) but I think it pushes things, in the right direction.
* Interceptors: think servlet filters but Grails aware, meaning you can call on services, and do redirect logic here. Although be careful, having uncaught errors, in here can cause you major headaches.

Grails Architecture:
![Grails Architecture](https://github.com/virtualdogbert/Grails_Architecture/raw/master/Grails_Architecture.png)

Grails Flow:
![Grails Flow](https://github.com/virtualdogbert/Grails_Architecture/raw/master/Grails_Flow.png)

{::nomarkdown}

<p xmlns:dct="http://purl.org/dc/terms/">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
  </a>
  <br />
  To the extent possible under law,
  <a rel="dct:publisher"
     href="https://github.com/virtualdogbert/Grails_Architecture">
    <span property="dct:title">Tucker Pelletier</span></a>
  has waived all copyright and related or neighboring rights to
  <span property="dct:title">Grails_Architecture</span>.
</p>

{:/}
