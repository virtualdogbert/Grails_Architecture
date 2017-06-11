# Grails_Architecture

High level breakdown of the parts of Grails:
* UrlMappings: Point incoming urls, from views, js or a seperate frontend, to controllers.
* Controllers: used for routing, rendering(views/strings), and calling services, maybe some light parameter checking*. Your business logic shouldn't be here.
* Services: where you business logic should be, and where you should manipulate domain objects.
* Views: rendered from controllers, to return html, json etc.
* Domains: These are your representation of your data source, often SQL tables, or NoSql objects. These can have constraint logic in them, but don't go overboard with, adding additional functions and logic, that should be in your services.
* Command objects: this is where you can do extensive parameter checking. They are like domain objects, but without the persistence. Command objects, don't currently have a convention other than they  implement the Validateable trait, and can be used to bind incoming params in controllers. I've actually written a plugin, that gives them more of a convention, which I'm just waiting to be included into the Grails plugin repo. The plugin isn't perfect yet(1.0) but I think it pushes things, in the right direction.
* Interceptors: think servlet filters but Grails aware, meaning you can call on services, and do redirect logic here. Although be careful, having uncaught error in here can cause you major headaches.

Grails Architecture:
![Grails Architecture](https://github.com/virtualdogbert/Grails_Architecture/raw/master/Grails_Architecture.png)

Grails Flow:
![Grails Flow](https://github.com/virtualdogbert/Grails_Architecture/raw/master/Grails_Flow.png)

