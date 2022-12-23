# NRT-automattion-course

- [NRT-automattion-course](#nrt-automattion-course)
  - [Main Topics](#main-topics)
  - [Tools list](#tools-list)


In June 2020 RGI commit decisions about tools and processes to adopt inside the company, his course will cover all aspects related to the implemetation of automatic test following lineguides and using standard tools defined.

## Main Topics 

The learning path is composed by these topics:

* [Setup develope workstation](./1_SETUP.md)
* [Basic concept]
* [RGI common libraries]
* [First test](2_FIRST_TEST.md)
* [Debugging]
* [Running]


## Tools list

* Playwright (Typesctript version)
* Cucumber
* Docker
* Jenkins
* dockerhost / swarm / kubernetes
  
Using the listed tools RGI created a standard stack to execute NRT tasks, produce reports, collect metrics and notify results. This stack is a cloud native implementation and it's possible run the stack in any enviroment that support container runtime (docker/swarm/kubernetes) so for example it's possible run all the stack also in a dev workstation with local docker setup.

