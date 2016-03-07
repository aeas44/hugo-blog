# Docker は何の役に立つの?

この記事は「[What does Docker provide if not virtualization?](https://opensource.com/business/14/8/docker-is-not-virtualization)」の翻訳記事です。

(画像)

Let me start by saying this is absolutely not a Docker bashing article. I actually love Docker, and I think it is an outstanding piece of software that will have great success. But I have to confess, I’m not sure that it deserves the virtualization moniker that so many in the industry are hanging on it.

まず最初に。この記事は Docker を批判するものではありません。私は Docker が大好きです。Docker は大きな成功を収めたソフトウェアだと思います。でも正直に言うと、これがソフトウェア業界を席巻している仮想化技術に匹敵するほどのものなのかについては分かりません。

Now before you start rounding up a virtual posse to excoriate me in the comments section for blasphemy, or heresy, hear me out.

おっと、よってたかってコメント欄で私を異端者と批難する前に、ちょっとだけ話を聞いてください。

First of all, I think, it is important to realize that often times in technology, especially leading edge technologies, it can be difficult for everyone to agree on a common definition of most any word. This is especially true in the cloud and virtualization vernacular. Generally speaking, for me, and for the context of this discussion, virtualization refers to the abstraction of a service(s) provided by an entity so that it can be consumed in a manner consistent with what the consuming entity expects, regardless of the characteristics of the entity providing the service. Or to say it in another manner: virtualization is the act of isolating the consumers of a service from the providers of a service in such a way so that each can maintain their native manner of interaction. This abstraction can be through simulation, emulation, translation, or another means, but the key function is making something, appear as something else, so it can be used.

技術の世界、それも先端技術の世界では筆致を尽くしても何かについて共通の定義を見出すのは難しいと認識すべきだと思います。クラウドや仮想化技術の世界では特に難しいです。一般に、私にとって、そしてこの議論において、仮想化とはエンティティによるサービスの抽象化であり、それはある手順によって消費されます。その手順とはエンティティが期待した通りのものであり、かつサービスに寄与しているエンティティの特性に依らないものです (訳注: 間違っていない訳だと思うが、こなれていないので推敲する)。別な言葉で言えば、仮想化とは隔離 (サービスのコンシューマとサービスのプロバイダの) で、それぞれが独立して機能できるようにするものです。この抽象化はシミュレーションやエミュレーション、翻訳 (訳注: 言語のではない)、もしくはその他の手段でなされます。しかし、肝心な機能は「何か」を「別な何か」に見えるようにし、使えるものにすることです。

For example, a hypervisor allows multiple discrete operating systems to consume a single physical server by abstracting the services provided by the server (CPU, Memory, Disk, etc) in such a way, that each operating system is oblivious to the true underlying characteristics of the server. It is that key functionality, of abstracting services, that Docker is lacking that stops me from bestowing the title of virtualization to it.

例えばハイパーバイザは複数の OS が物理的に一つのサーバを消費することを許します。これはサーバ (CPU、メモリ、ディスクなど) を抽象化することで実現されています。それぞれの OS はベースとなるマシンの特性を意識することはありません。これこそがサービスの抽象化に必要なことです。この観点において、私は Docker を「仮想化技術」と呼べないのです。

Many of you may very well be thinking right now, "Docker does provide virtualization to applications. It virtualizes the operating system for them." My response is to submit, respectfully, that Docker doesn’t actually abstract or virtualize anything. It is a software package that manages several, normally discrete, Linux features, in a manner so that they all work cooperatively to provide a given functionality. Docker, unlike say a Hypervisor, doesn’t isolate away or abstract services to a consumer. Docker, not so simply, serves as a conductor to orchestrate all the various services together and have them work cooperatively. It is even valid to go so far as to say that Docker isn’t a required component of providing the service that the application consumes.

みなさんはこう思っていることでしょう。「Docker はアプリケーションを仮想化しているよ。アプリケーションのために OS を仮想化しているよね」。それに対する私の答えは「Docker は抽象化も仮想化も実際にはしていないよ」です。もちろん、敬意を込めての返答です。Docker は複数の、通常は分散した、Linux 機能を管理するソフトウェア・パッケージです。この分散した機能は協調して動きます。ハイパーバイザと違い、Docker はコンシューマに対してサービスを隔離しません。Docker はそう単純でなく、指揮者として異なるサービスをまとめ上げ協調させるのです。こうとすら言えるでしょう。Docker はアプリケーションが利用するサービスを提供するのに必要なコンポーネントではない、と。

Now having said that, I should add that even though I feel like I’m a fairly advanced administrator, I could not even imagine taking on the tasks that Docker performs in manual process. It is simply too daunting of a task, due to the plethora of dependencies, lack of understanding all of the features being used, and lack of robustness in the management tools. To those that would offer "Just write a script," I would respond with "Why, when Docker does it for us?"

したがって、私は自分が経験のあるサーバ管理者であるように思うけれど、それでも Docker がマニュアルで行うタスクを管理したいとは思わないのです。依存関係が多すぎること、使われている機能の理解に欠こと、管理ツールの堅牢性に欠けることなどのせいで、単に気の進まない仕事です。単に「スクリプトを書け」と言う人たちに対して、「Docker はいつ我々のためにそうしてくれるの?」と返します。

Docker really is, in my opinion, a great piece of software. I will confess that I haven’t reviewed the code, I’m not a developer. My job, if you will indulge an oversimplification, is to make things work. Docker does that, and it seems to do so in a very efficient, logical, and productive manner. I am very excited about the future of Docker and how the functionality (or services) that it orchestrates will impact not only development, but also operations and engineering teams within an organization.

Docker は偉大なソフトウェアだと思います。デベロッパーではないので、コードを詳しく読んだことはありません。とても簡単に言えば、私の仕事は「ものを動かす」ことです。Docker はそのためのものです。効率的に、論理的に、Docker はそれを実現してくれます。Docker が将来において、そのサービスのオーキストレーション機能でもって、開発のみでなく運用チームに貢献することを楽しみに思っています。
