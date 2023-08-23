<img src="https://raw.githubusercontent.com/matiassingers/awesome-readme/master/icon.png" align="right" />

# Dos attack in browser [![Awesome](https://cdn.jsdelivr.net/gh/sindresorhus/awesome@d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome#readme)
> **Warning**
> Be careful running this with elevated privileges. Code execution can be achieved with write permissions on the config file.

Elements in beautiful READMEs include, but are not limited to: images, screenshots, GIFs, text formatting, etc.

<br />

### Video. How it is work ?
[![CLICK ME TO PLAY](https://i.ytimg.com/vi/Hc79sDi3f0U/maxresdefault.jpg)](https://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)

### Built With
* 🌐
* 🧪

# 🤖 🚀 Introduction

🤹 ZenML is an extensible, open-source MLOps framework for creating portable,
production-ready machine learning pipelines. By decoupling infrastructure from
code, ZenML enables developers across your organization to collaborate more
effectively as they develop to production.

- 💼 ZenML gives data scientists the freedom to fully focus on modeling and
experimentation while writing code that is production-ready from the get-go.

- 👨‍💻 ZenML empowers ML engineers to take ownership of the entire ML lifecycle
  end-to-end. Adopting ZenML means fewer handover points and more visibility on
  what is happening in your organization.

- 🛫 ZenML enables MLOps infrastructure experts to define, deploy, and manage
sophisticated production environments that are easy to use for colleagues.

![The long journey from experimentation to production.](/docs/book/.gitbook/assets/intro-zenml-overview.png)

ZenML provides a user-friendly syntax designed for ML workflows, compatible with
any cloud or tool. It enables centralized pipeline management, enabling
developers to write code once and effortlessly deploy it to various
infrastructures.

<div align="center">
    <img src="docs/book/.gitbook/assets/stack.gif">
</div>

# 🤸 Quickstart

[Install ZenML](https://docs.zenml.io/getting-started/installation) via
[PyPI](https://pypi.org/project/zenml/). Python 3.8 - 3.11 is required:

```bash
pip install "zenml[server]"
```

Take a tour with the guided quickstart by running:

```bash
zenml go
```

# 🖼️ Create your own MLOps Platform

ZenML allows you to create and manage your own MLOps platform using 
best-in-class open-source and cloud-based technologies. Here is an example of 
how you could set this up for your team:

## 🔋 1. Deploy ZenML

For full functionality ZenML should be deployed on the cloud to
enable collaborative features as the central MLOps interface for teams.

![ZenML Architecture Diagram.](docs/book/.gitbook/assets/Scenario3.png)

Currently, there are two main options to deploy ZenML:

- **ZenML Cloud**: With [ZenML Cloud](https://docs.zenml.io/deploying-zenml/zenml-cloud), 
you can utilize a control plane to create ZenML servers, also known as tenants. 
These tenants are managed and maintained by ZenML's dedicated team, alleviating 
the burden of server management from your end. 

- **Self-hosted deployment**: Alternatively, you have the flexibility to [deploy 
ZenML on your own self-hosted environment](https://docs.zenml.io/deploying-zenml/zenml-self-hosted). 
This can be achieved through various methods, including using our CLI, Docker, 
Helm, or HuggingFace Spaces.

## 👨‍🍳 2. Deploy Stack Components

ZenML boasts a ton of [integrations](https://zenml.io/integrations) into 
popular MLOps tools. The [ZenML Stack](https://docs.zenml.io/user-guide/starter-guide/understand-stacks) 
concept ensures that these tools work nicely together, therefore bringing
structure and standardization into the MLOps workflow.

Deploying and configuring this is super easy with ZenML. For **AWS**, this might 
look a bit like this

```bash
# Deploy and register an orchestrator and an artifact store
zenml orchestrator deploy kubernetes_orchestrator --flavor kubernetes --cloud aws
zenml artifact-store deploy s3_artifact_store --flavor s3

# Register this combination of components as a stack
zenml stack register production_stack --orchestrator kubernetes_orchestrator --artifact-store s3_artifact_store --set # Register your production environment
```

When you run a pipeline with this stack set, it will be running on your deployed
Kubernetes cluster.

You can also [deploy your own tooling manually](https://docs.zenml.io/stacks-and-components/stack-deployment).

## 🏇 3. Create a Pipeline

Here's an example of a hello world ZenML pipeline in code:

```python
# run.py
from zenml import pipeline, step


@step
def step_1() -> str:
    """Returns the `world` substring."""
    return "world"


@step
def step_2(input_one: str, input_two: str) -> None:
    """Combines the two strings at its input and prints them."""
    combined_str = input_one + ' ' + input_two
    print(combined_str)


@pipeline
def my_pipeline():
    output_step_one = step_1()
    step_2(input_one="hello", input_two=output_step_one)


if __name__ == "__main__":
    my_pipeline()
```

```bash
python run.py
```

## 👭 4. Start the Dashboard

Open up the ZenML dashboard using this command.

```bash
zenml show
```

![ZenML Dashboard](docs/book/.gitbook/assets/landingpage.png)

# 🗺 Roadmap

ZenML is being built in public. The [roadmap](https://zenml.io/roadmap) is a
regularly updated source of truth for the ZenML community to understand where
the product is going in the short, medium, and long term.

ZenML is managed by a [core team](https://zenml.io/company#CompanyTeam) of
developers that are responsible for making key decisions and incorporating
feedback from the community. The team oversees feedback via various channels,
and you can directly influence the roadmap as follows:

- Vote on your most wanted feature on our [Discussion
  board](https://zenml.io/discussion).
- Start a thread in our [Slack channel](https://zenml.io/slack-invite).
- [Create an issue](https://github.com/zenml-io/zenml/issues/new/choose) on our
  GitHub repo.

# 🙌 Contributing and Community

We would love to develop ZenML together with our community! Best way to get
started is to select any issue from the [`good-first-issue`
label](https://github.com/zenml-io/zenml/labels/good%20first%20issue). If you
would like to contribute, please review our [Contributing
Guide](CONTRIBUTING.md) for all relevant details.

# 🆘 Getting Help

The first point of call should
be [our Slack group](https://zenml.io/slack-invite/).
Ask your questions about bugs or specific use cases, and someone from
the [core team](https://zenml.io/company#CompanyTeam) will respond.
Or, if you
prefer, [open an issue](https://github.com/zenml-io/zenml/issues/new/choose) on
our GitHub repo.

# 📜 📘 License

ZenML is distributed under the terms of the Apache License Version 2.0.
A complete version of the license is available in the [LICENSE](LICENSE) file in
this repository. Any contribution made to this project will be licensed under
the Apache License Version 2.0.










<!--# Dos_attack_in_browser


## How it Works
your explanation...

## Getting started](#get-started)
your explanation...

## [Contributing](#contributing)
your explanation...

## [Core team](#core-team)
your explanation...

## [License](#license)
your explanation...


## Установка и Автозагрузка

Этот пакет сопровождается файлом [composer.json][], что позволяет использовать 
[Composer][] для его инсталляции и автозагрузки.

Так же можно установить его загрузив [исходные коды][] пакета в виде Zip архива 
или клонировав этот репозиторий. Все компоненты этого пакета загружают 
зависимости автоматически.

Перед использованием рекомендуется выполнить тестирование с помощью утилиты 
[PHPUnit][] вызвав ее в корневом каталоге пакета.


## Поддержка

Если у вас возникли сложности или вопросы по использованию пакета, создайте 
[обсуждение][] в данном репозитории или напишите на электронную почту 
<Artur-Mamedbekov@yandex.ru>.

## Документация

Пользовательскую документацию можно получить по [ссылке](./docs/index.md).

Документацию API можно получить из исходных кодов пакета или с помощью утилиты 
[Doxygen][].

[composer.json]: ./composer.json
[Composer]: http://getcomposer.org/
[исходные коды]: https://github.com/Bashka/bricks_cli_routing/releases
[PHPUnit]: http://phpunit.de/
[обсуждение]: https://github.com/Bashka/bricks_cli_routing/issues
[Doxygen]: http://www.stack.nl/~dimitri/doxygen/index.html
# Video. How it is work?
[<img src="https://i.ytimg.com/vi/Hc79sDi3f0U/maxresdefault.jpg" width="50%">](https://www.youtube.com/watch?v=Hc79sDi3f0U "Now in Android: 55")
[![CLICK ME TO PLAY](https://i.ytimg.com/vi/Hc79sDi3f0U/maxresdefault.jpg)](https://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)
[![Everything Is AWESOME](https://img.youtube.com/vi/StTqXEQ2l-Y/0.jpg)](https://www.youtube.com/watch?v=StTqXEQ2l-Y "Everything Is AWESOME")-->
