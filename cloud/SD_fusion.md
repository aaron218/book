# 大数据系统的超融合

## 软件定义
软件定义，其实在很大程序上是计算机中操作系统的虚拟性更进一步的展现，进一步把系统对硬件的虚拟性扩展到了各个方面。因而，在这里，我们认为软件定义的本质就是虚拟一切。

软件定义的就像是电传系升级到程控系统，带来的不仅仅是管理模式的提升，更多的是效率的革命性变化。
例如手机大小一个小小的软件定义无线电(SDR)，就可以完整一整套无线电基站的功能。而手机的SoC，本质上何尝又不是一个软件定义主机？

由于硬件的性能不断提升，软件可以以更高的效率模拟硬件，同时也可以更高效的控制硬件。计算机科学的两条腿互相协助，步子是迈的越来越快。

包括目前的HDFS文件系统在内，通过软件提供的原硬件能力已经越来越多，软硬件的界限对于应用层已经越来越模糊。

## 超融合
超融合是近些年来提出的一种服务模式，在一个机柜中，将数据的传输、存储、运算乃至业务服务都一并提供。超融合不仅仅是软件系统的融合，更是硬件设备的融合。

由于可以在一台机柜中完成存储，运算，甚至能够实现在本地的集群高可用性，使得超融合硬件从诞生开始就快速的向之前被分布式系统平台所占领的领域突进。

目前包括HANA、vSAN在内的超融合方案已经广泛运用于高端数据处理场景，提供了传统的分布式系统难以企及的高效高速服务能力。同时也带走了大量的企业预算。



> 软件定义与超融合，是一个互相竞争有互相吸收的两类解决方案。

## 数据支撑系统
广义的数据支撑系统一般被叫做数据服务平台DSP(Data Service Platform)，
与相对狭义的数据支撑系统(DSS Data Support System)相比，主要是在数据的使用和运营上下了更多功夫，也就是更加接近应用层。

但是这种对应用的接近，使得DSP具有相当高的领域特性。而DSS主要应该专注于数据的IO服务，
相较于更加底层的统一文件访问支持，DSS则提供了统一的数据访问支持。在产业上，这两个概念可以分别对应Alluxio和Ignite两大统一资源访问系统。
（与Swift和Ceph的关系不同，此二者常有争论，但是就初衷而言，Alluxio是提供了统一的文件资源访问，较少的关注内奸内部的结构，而Ignite是聚焦于统一的使用数据）
