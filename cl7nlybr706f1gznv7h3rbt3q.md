## NeuBrain - My first SaaS using Flutter and Rust (Soon!)

# 🤔 Problem Statement 

Currently, I'm trying to improve my English and Japanese skills, and I have experience with various language learning applications like [Duolingo](https://www.duolingo.com/), [Memrise](https://www.memrise.com/), [Elsa Speak](https://elsaspeak.com/en/), [Busuu](https://www.busuu.com/), and even classic application [Anki](https://apps.ankiweb.net/).

I still cannot improve those skills efficiently enough, and most of them do not fit my learning methodologies.

My core learning methodologies:
- Spaced Repetition
- Connections

## Spaced Repetition

![Spaced Repetition](https://upload.wikimedia.org/wikipedia/commons/a/ae/Leitner_system_animation.gif)
> https://en.wikipedia.org/wiki/Spaced_repetition

[Spaced Repetition](https://en.wikipedia.org/wiki/Spaced_repetition) is a well-known technique to remember things based on scientific evidence. I learned this technique from the course called ["Learning How to Learn"](https://www.coursera.org/learn/learning-how-to-learn) from Coursera, and it's sparked me since then. So I pretty much recommend you to take this class, and it will help you a lot to learn the most efficient method based on proven evidence.

## Connections

The connection technique is one of the most common learning techniques I find everywhere I read or learn, such as the Learning How to Learn course as above, an idea behind the scene of [Obsidian](https://obsidian.md/), [Zettelkasten](https://en.wikipedia.org/wiki/Zettelkasten) methodology, and a [Fluent Forever](https://www.goodreads.com/book/show/19661852-fluent-forever) book. Linking existing knowledge and connecting the dots will strengthen that knowledge and skills.

---

# 💡 The Idea 

After searching for many applications, I decided to create an application and will publish it as my first SaaS.

At first, this idea was intended to be a project for [Redis Hackathon](https://dev.to/devteam/announcing-the-redis-hackathon-on-dev-3248), but unfortunately, it supposes to publish source code to the public, and this might not be good for the business in the future.

The application will support macOS, Windows, iOS, Android, and Web platforms because I want it to be more convenient for all learners, even though they are commuting or sitting in front of the laptop.

The name **"NeuBrain"** came to my mind at the time, and I decided to start to work on this project intensely after my working hours.

---

# 🤖 Tech Stack - Client

I used to decided to choose [Tauri](https://tauri.app/) as the client framework because I want to practice [Rust](https://www.rust-lang.org/) and [Svelt](https://svelte.dev/). But it seems like Tauri doesn't support mobile platforms yet. So maybe I may use this stack for the next project instead.

## Flutter

![Google-flutter-logo.svg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662306001945/nS_2l6c7r.png align="left")

So, [Flutter](https://flutter.dev/) is the better choice. Unfortunately, I have experience developing applications using Flutter around 6-7 months ago. Still, I can implement it fluently, and it's a perfect opportunity to sharpen my Flutter skill to the next level.

With the power of Flutter, which is written in Dart, we can implement applications only once and publish them to desktop, mobile, and web with ease.

To explore new areas related to Flutter, I designed the application to use [Atomic Design Methodology](https://bradfrost.com/blog/post/atomic-web-design/) combined with [Hexagonal Architecture](https://en.wikipedia.org/wiki/Hexagonal_architecture_(software)).

### Atomic Design

![atomic-design.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662306270091/Koy36P6z_.png align="left")
> https://bradfrost.com/blog/post/atomic-web-design/

Atomic Design allows me to create components into each category and combine them into more significant parts with well organized.

I heard about this methodology a lot, but this is my first time applying the method. It may confuse you at first about which components should be atoms, molecules, or organisms. But once you get your hand dirty and try using it enough, it will bring you a sense of how to choose at last.


```
- core/
- modules/
- ui/
-- tokens/
---- colors.dart
---- sizes.dart
---- typography.dart
---- ...
-- foundations/
---- themes/
------ light.dart
------ dark.dart
---- colors.dart
---- sizes.dart
---- typography.dart
---- ...
-- atoms/
---- button.dart
---- logo.dart
---- spacer.dart
---- ...
-- molecules/
---- deck.dart
---- search.dart
---- ...
-- organisms/
---- appbar.dart
---- section.dart
---- ...
-- templates/
---- main_template.dart
---- study_template.dart
---- ...
-- pages/
---- main_page.dart
---- study_page.dart
---- ...
``` 

The `ui` folder will contain only presentation views without any business logic, while `core` will contain shared functionality, and `modules` will contain business logic.

### Hexagonal Architecture
![1000px-Hexagonal_Architecture.svg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662307423058/jE55fvssl.png align="left")
> https://en.wikipedia.org/wiki/Hexagonal_architecture_(software)

Hexagonal Architecture allows the ability to change technology by abstracting the technology agnostic. I still do not see many applications using this architecture that much with Flutter. But I would like to know how far this idea will suit best in the long term.

```
- core/
- modules/
-- (feature)
---- adapters/
------ http.dart
------ secured_storage.dart
------ ...
---- domain/
------ entities/
-------- card.dart
-------- ...
------ services/
-------- create_cart.dart
-------- ...
---- ports/
------ api. Dart
------ storage.dart
------ ...
- ui/
``` 

If you want to learn how this idea works, I suggest you read [this article](https://medium.com/@matiasvarela/hexagonal-architecture-in-go-cfd4e436faa3). It may be hard to understand at first but bear with it, and it's worth trying and good for you in the long run.

Remember, if you're struggling with it, try to keep motivated because you're going to climb the mountain named learning curve and overcome it.

# 🤖 Tech Stack - Server

## Rust
![Rust_programming_language_black_logo.svg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662308163730/GezqVMsAH.png align="left")
> https://en.wikipedia.org/wiki/Rust_(programming_language)

Rust is still the priority language I want to be an expert in. I intend to let every side project be my sandbox to learn things I'm passionate about.

It's pretty challenging, and we will see how far it will take me to which level.

And yes! I will use Hexagonal Architecture for Rust as well.

## Redis Stack
![redis-stack-blog-logo.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1662308595917/8YLjI-lqv.webp align="left")
> https://redis.com/blog/introducing-redis-stack/

As I mentioned earlier, this project was intended to be a hackathon. , and the [Redis Stack]
(https://redis.io/docs/stack/) is one of my choices as the primary data store (with persistence setting).

We can store, search, and create a relation graph in real-time with the Redis Stack. So, it is the perfect data store for this project.

##  Google Cloud Platform
![social-icon-google-cloud-1200-630.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662308964015/RXW711lN5.png align="left")
> https://cloud.google.com/

This is still a tentative choice because I'm currently developing the NeuBrain on the local machine. I need to research which platform will be a good companion and affordable for this project.

I used to create entire [Kubernetes](https://kubernetes.io/) cluster by using [Terraform](https://www.terraform.io/) once. But this time, if the GCP is eventually perfect, I would try something more advanced from that for learning purposes and [Google Cloud Certifications](https://cloud.google.com/certification). 

---

# 👨🏻‍🎓 Lesson Learned

I have learned a lot so far from this project, and it has 50% in progress now. I learned something new like Rust and Redis Stack and enhanced existing skills such as Flutter and GCP.

I used to publish the applications using Flutter for web and mobile devices, but this is the first time I have published it in a desktop environment. I will learn from this implementation a lot.

I'm working on this project intensely, and I'm thrilled to launch it soon.

Subscribe to my newsletter below. Once the application is launched, I'll let you know first!

Stay tuned!

Get to know me:
- [GitHub](https://github.com/notsu)
- [Linkedin](https://www.linkedin.com/in/notsu/)
- [Twitter](https://twitter.com/notsu)

---