# Welcome to the Nusantara NLP Hackathon!


![progress claimed](https://progress-bar.dev/0/?title=Datasets%20Claimed)

![tier1](https://progress-bar.dev/0/?title=Progress%201%20(30%20Datasets%20Completed))
![tier2](https://progress-bar.dev/0/?title=Progress%202%20(60%20Datasets%20Completed))
![tier3](https://progress-bar.dev/0/?title=Progress%203%20(100%20Datasets%20Completed))
![tier4](https://progress-bar.dev/0/?title=Progress%204%20(150%20Datasets%20Completed))

Nusantara NLP🌸 initative is an open scientific collaboration of hundreds Indonesian NLP researchers from various countries and institutions who collaborate on collecting and advancing natural language processing (NLP) resources for Indonesian and its 700+ local languages to broaden accessibility of language datasets while working on challenging scientific questions around language modeling.

We are running a **Nusantara NLP Datasets hackathon** to centralize many NLP datasets in Indonesian and local languages. Indonesian languages are diverse and scattered, so a unified location that joins multiple sources while preserving the data closest to the original form can greatly help accessibility.

## Goals of this hackathon

Our goal is to **enable easy programatic access to these datasets** using Huggingface's (🤗) [`datasets` library](https://huggingface.co/docs/datasets/). To do this, we propose a unified schema for dataset extraction, with the intention of implementing as many datasets as possible to enable **reproducibility in data processing**. 

There are two broad licensing categories for datasets:

##### 1. Public Data (Public Domain, Creative Commons, Apache 2.0, etc.)
##### 2. External Data Use Agreements

We will accept data-loading scripts for either type; please see the [FAQs](#FAQs) for more explicit details on what we propose.

### Why is this important?

Textual data of Indonesian languages, especially for local languages, is extremely low-resource and under represented globally. Many great initiatives have created different language data sets across a variety of languages. A **centralized source that allows users to access relevant information reproducibly** greatly increases accessibility of these datasets, and promotes research.

Our unified schema allows researchers and practioners to **access the same type of information across a variety of datasets with fixed keys**. This can enable researchers to quickly iterate, and write scripts without worrying about pre-processing nuances specific to a dataset.

## Contribution Guidelines

To be considered a contributor, participants must implement an *accepted data-loading script* to the nusantara-nlp collection for **at least 3 datasets**. 

Explicit instructions are found in the next section, but the steps for getting a data-loading script accepted are as follows: <br>

- Fork this repo and write a data-loading script in a new branch
- PR your branch back to this repo and ping the admins
- An admin will review and approve your PR or ping you for changes

Details for contributor acknowledgements and rewards can be found [here](#Thank-you)

## Get started!

### 1. Choose a dataset to implement

There are two options to choose a dataset to implement; you can choose either option, but **we recommend option A**. 

**Option A: Assign yourself a dataset from our curated list**
- Choose a dataset from the [list of Nusantara datasets](https://github.com/orgs/indobenchmark/projects/1/views/1). 
<p align="center">
    <img src="./docs/_static/img/select-task.jpeg" style="width: 80%;"/>
</p>

- Assign yourself an issue by clicking the dataset in the project list, and comment `#self-assign` under the issue. **Please assign yourself to issues with no other collaborators assigned**. You should see your GitHub username associated to the issue within 1-2 minutes of making a comment.
<p align="center">
    <img src="./docs/_static/img/self-assign.jpg" style="width: 80%;"/>
</p>

- Search to see if the dataset exists in the 🤗 [Hub](https://huggingface.co/datasets). If it exists, please use the current implementation as the `source` and focus on implementing the [task-specific `nusantara` schema](https://github.com/indobenchmark/nusantara-datasets/blob/master/task_schemas.md). 

**Option B: Implement a new dataset not on the list**

If you have a Indonesian and local languages dataset you would like to propose in this collection, you are welcome to [make a new issue](https://github.com/indobenchmark/nusantara-datasets/issues/new) and fill out relevant information. **Make sure that your dataset does not exist in the 🤗 [Hub](https://huggingface.co/datasets).**

If an admin approves it, then you are welcome to implement this dataset and it will count toward contribution credit.

### 2. Implement the data-loading script for your dataset and create a PR

[Check out our step-by-step guide to implementing a dataloader with the nusantara schema](CONTRIBUTING.md).

**Please do not upload the data directly; if you have a specific question or request, [reach out to an admin](#Community-channels)**

As soon as you have opened a PR, the dataset will be marked as `In Progress` in the
[list of Indonesian datasets](https://github.com/orgs/indobenchmark/projects/1/views/1).
When an admin accepts the PR and closes the corresponding issue, the dataset will be
marked as `Done`.

## Contribution reward

Coming soon.

## Community channels

We welcome contributions from a wide variety of backgrounds; we are more than happy to guide you through the process. For instructions on how to get involved or ask for help, check out the following options:

#### Join our Slack Channel
Alternatively, you can ping us on the [Slack Channel](). The Slack channel can be used to share information quickly or ask code-related questions.

#### Make a Github Issue
For quick questions and clarifications, you can [make an issue via Github](https://github.com/indobenchmark/nusantara-datasets/issues/new).

You are welcome to use any of the above resources as necessary. 

## FAQs

#### How can I find the appropriate license for my dataset?

The license for a dataset is not always obvious. Here are some strategies to try in your search,

* check for files such as README or LICENSE that may be distributed with the dataset itself
* check the dataset webpage
* check publications that announce the release of the dataset
* check the website of the organization providing the dataset

If no official license is listed anywhere, but you find a webpage that describes general data usage policies for the dataset, you can fall back to providing that URL in the `_LICENSE` variable. If you can't find any license information, please make a note in your PR and put `_LICENSE="Unknown"` in your dataset script.   

#### What if my dataset is not publicly available?

We understand that some datasets are not publicly available due to data usage agreements or licensing. For these datasets, we recommend implementing a dataloader script that references a local directory containing the dataset. You can find examples in the [n2c2_2011](examples/n2c2_2011.py) and [bioasq](examples/bioasq.py) implementations. There are also local dataset specific instructions in  [template](templates/template.py).

#### What types of libraries can we import?

Eventually, your dataloader script will need to run using only the packages supplied by the [datasets](https://github.com/huggingface/datasets) package. If you find a well supported package that makes your implementation easier, then feel free to use it.  We will address the specifics during review of your PR to the [Nusantara NLP repo](https://github.com/indobenchmark/nusantara-datasets).

#### Can I upload my dataset anywhere?

No. Please don't upload the dataset you're working on to the huggingface hub or anywhere else.  This is not the goal of the hackathon and some datasets have licensing agreements that prevent redistribution. If the dataset is public, include a downloading component in your dataset loader script. Otherwise, include only an "extraction from local files" component in your dataset loader script. If you have a custom dataset you would like to submit, please [make an issue](https://github.com/indobenchmark/nusantara-datasets/issues/new) and an admin will get back to you.  

#### My dataset supports multiple tasks with different nusantara schemas. What should I do? 

In some cases, a single dataset will support multiple tasks with different nusantara schemas. For example, the `muchmore` dataset can be used for a translation task (supported by the `Text to Text (T2T)` schema) and a named entity recognition task (supported by the `Knowledge Base (KB)` schema). In this case, please implement one config for each supported schema and name the config `<datasetname>_nusantara_<schema>`. In the `muchmore` example, this would mean one config called `muchmore_nusantara_t2t` and one config called `muchmore_nusantara_kb`.  

#### My dataset comes with multiple annotations per text and no/multiple harmonizations. How should I proceed?

Please implement all different annotations and harmonizations as `source` versions (see [examples/bioasq.py](examples/bioasq.py) for an example).
If the authors suggest a preferred harmonization, use that for the `nusantara` version.
Otherwise use the harmonization that you think is best.

#### How should I handle offsets and text in the nusantara schema?

Full details on how to handle offsets and text in the nusantara kb schema can be found in the [schema documentation](https://github.com/indobenchmark/nusantara-datasets/blob/master/task_schemas.md).

#### My dataset is complicated, can you help me?

Yes! Please join the hack-a-thon [Slack Channel]() and ask for help. 

#### My dataset is too complicated, can I switch?

Yes! Some datasets are easier to write dataloader scripts for than others. If you find yourself working on a dataset that you can not make progress on, please make a comment in the associated issue, asked to be un-assigned from the issue, and start the search for a new unclaimed dataset. 

#### Can I change the Nusantara schema?

**No, please do not modify the Nusantara Schema.** The goal of this hackathon is to enable simple, programmatic access to a large variety of datasets. Part of this requires having a dependable interface. We developed our schema to address the most salient types of questions to ask of the datasets. We would be more than happy to discuss your suggestions, and you are welcome to implement it as a new config.

#### My dataset has multiple labels for a span of text - what do I do?

In many of our schemas, we have a 1:1 mapping between a key and its label (i.e. in KB, entity and label). In some datasets, we've noticed that there are multiple labels assigned to a text entity. Generally speaking, if a nusantara key has multiple labels associated with it, please populate the list with multiple instances of (key, label) according to each label that correspond to it. 

So for instance if the dataset has an entity "copper" with the  types "Pharmacologic Substance" and "Biologically Active", please create one entity with type "Pharmacologic Substance" and an associated unique id *and* another entity with type "Biologically Active" with a different unique id. The rest of the inputs (text, offsets, and normalization) of both entities will be identical.

#### What happens after I claim a dataset?
In order to keep turnaround time reasonable, and ensure datasets are being completed, we propose a few notes on claiming a dataset:

* Please claim a dataset only if you intend to work on it. We'll try to check in within 3 days to ensure you have the help you need. Don't hesitate to contact the admins! We are ready to help 💪!

* If you have already claimed a dataset prior to (2022/06/01), we will check in on **Friday (2022/06/10)**. If we do not hear back via GitHub issues OR a message to the Discord admins on general, we will make the dataset open for other participants by **Saturday (2022/06/11)**.

* If things are taking longer than expected - that is totally ok! Please let us know via GitHub issues (preferred) or by pinging the @admins channel on Slack.

## Thank you!

We greatly appreciate your help! 

The artifacts of this hackathon will be described in a forthcoming academic paper targeting a machine learning or NLP audience. Please refer to [this section](#contribution-reward) for your contribution rewards for helping Nusantara NLP. We recognize that some datasets require more effort than others, so please reach out if you have questions. Our goal is to be inclusive with credit!

<!-- 
## Acknowledgements

This hackathon guide was heavily inspired by [the BigScience Datasets Hackathon](https://github.com/bigscience-workshop/data_tooling/wiki/datasets-hackathon).
 -->
