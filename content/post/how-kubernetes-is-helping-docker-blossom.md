# いかにして Kubernetes は Docker の盛り上がりに寄与しているのか

(この記事は「[How Kubernetes is helping Docker blossom](https://opensource.com/business/16/1/scale14x-interview-jason-brooks-red-hat)」の翻訳です)

![いかにして Kubernetes は Docker の盛り上がりに寄与しているのか](/images/posts/2016-03-kubernetes/containers_2015-1-osdc-lead.png)

[Kubernetes](http://kubernetes.io/) と [Docker](https://www.docker.com/) は、いずれも IT 業界におけるトレンドとなっています。ビジネスやコンピュータに熱心な人たちはコンテナ技術についてさらに深く学ぼうとしています。

幸いなことに Red Hat でソフトウェア・アナリストをしている [Jason Brooks] に、コンテナ技術の最新動向について聞くことができました。彼は [SCaLE 14x](https://opensource.com/resources/scale-14x) で Kubernetes について話す予定です。

![QA](/images/posts/2016-03-kubernetes/Interview-banner-QA.png)

## すでに Docker に馴染みがあり、これから Kubernetes を学ぼうとしている人たちに何を伝えたいですか?

Kubernetes は Docker を複数ホストでの運用に拡張します。(Docker 関連のプロジェクトは全てそうですけど) Kubernetes は比較的新しいプロジェクトです。一方で、 Google の長年のコンテナ運用技術の結晶でもあります。この出自にも関わらず、Kubernetes は多くのコントリビュータによって支えられており、結果として様々なユースケースやアイディアが反映されたプロジェクトとなっています。試しに通常の Docker ホストで触ってみたければ、[こちらの記事](https://github.com/kubernetes/kubernetes/blob/release-1.1/docs/getting-started-guides/docker.md)を参考にしてください。

## Kubernetes はホビー・プログラマが開発しているのでしょうか? それとも大企業が自社のために開発しているのでしょうか?

I haven't looked at this definitively. I know that the use case is applicable for hobbyist-sized needs—applications of many shapes and sizes benefit from running across multiple machines. I work for a large company, but the use case I'm talking about at SCaLE, the running of a test lab, isn't limited to a large organization.

これについて詳しく調べたことはありません。私が言えるのは Kubernetes は様々な形態やサイズのアプリケーションに適用可能だということです。私自身も大企業で働いていますが、SCaLE で話すユースケースは大企業だけにあてはまるものではありません。

## Kubernetes はクラスタ環境におけるコンテナ化されたアプリケーションのデプロイとスケーラビリティのためのツールですね。これはコンテナの流行にどう関連しているのでしょうか?

Docker をコンテナ運送に例えるのは魅力的なアイディアです。しかし、コンテナだけでは運河を渡り切ることはできません。コンテナの流行を一過性のものでなくするためには、コンテナを開発者のノートパソコンからプロダクションに降ろしてやる必要があります。この作業に Kubernetes が一役買ってしているのです。

## 将来 Kubernetes に移行するとしたら、どのような作業が求められるでしょうか?

I think the sky's the limit. That's part of what I'm talking about at SCaLE—things like distributed storage and virtualization that you might not expect to run in containers, but that you do want to run reliably and flexibly across a set of machines.

やろうとすれば、何でもできます。SCaLE ではこのことも話そうと思います。分散ストレージや仮想化もその一部です。これらの技術はコンテナとは関係ないように思えるかもしれません。しかし複数のマシンを柔軟に使いたいとは思いますよね (だから、こういうものが欲しくなりますよね)。

## Kubernetes は多くのプラットフォームで動作しますね。マルチプラットフォームの実現はどのくらい大変なのですか?

これについては、たくさんのコントリビュータが手伝ってくれています。コントリビュータごとに、気にかけるプラットフォームやユースケースが違うのです。結果として、多くのプラットフォームがサポートされています。

## これらの環境をテストするための自動化されたセットアップ手順はありますか?

全ての環境を試してみたわけではありませんが、通常は [Fedora](https://getfedora.org/) や [CentOS](https://www.centos.org/) による[Atomic](http://www.projectatomic.io/download/) プロジェクト、そして [Ansible](http://ansible.com/) や [Vagrant](https://www.vagrantup.com/) で環境構築の自動化をしています。([くわしくはこちら](http://www.projectatomic.io/blog/2015/09/clustering-atomic-hosts-with-kubernetes-ansible-and-vagrant/))。

## この数年間で Kubernetes はどのように進化するでしょうか? 大きな目標はありますか?

短期的には [SELinux](https://en.wikipedia.org/wiki/Security-Enhanced_Linux) に関する問題解決と Kubernetes コンポーネント自身をコンテナの中で動かすことです。また、複数のコンテナ化エンジンのサポートや、[Mesos](http://mesos.apache.org/) などの他のリソース管理ツールとの協調にも興味があります。

## SCaLE 14x Series

SCaLE はコミュニティにより運営されている、オープンソースまたはフリーソフトウェアに関する北アメリカの大規模カンファレンスです。「The Scale 14x」シリーズでは、スピーカーとしての登壇が予定されている方に、イベントに先駆けてインタビュー記事を掲載しています。

## ライセンス

原文は [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/) で提供されています。本記事も同ライセンスに従います
