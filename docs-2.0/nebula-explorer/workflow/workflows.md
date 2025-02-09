# 工作流简介

{{explorer.name}}支持用自定义工作流进行可视化的复杂图计算。

## 背景信息

{{explorer.name}}提供多种**组件**（Component），包括图查询组件和图计算组件，用户可以基于编排调度工具 Dag Controller 自由组合这些组件，例如将图查询组件的输出作为图计算组件的输入，最终形成一个有向无环的**工作流**（Workflow）。

![workflow-example](https://docs-cdn.nebula-graph.com.cn/figures/ex-workflow-example-220621.png)

需要进行图计算时再将工作流实例化，组件实例化后称为**任务**（Task），工作流实例化后称为**作业**（Job）。一个作业可以由多个任务构成。{{explorer.name}}将作业发送给{{plato.name}}进行图计算，完成后可以在作业列表查看对应的图计算结果。

## 功能说明

- 支持新增、查看、修改、删除、对比、克隆、重命名工作流。
- 支持查询组件和多种算法组件，可以搜索、新增、配置、重命名组件。
- 支持查看作业列表、进度、结果、日志，以及重跑作业。
- 支持搜索工作流或作业。

## 注意事项

- 需要在 ![setting](https://docs-cdn.nebula-graph.com.cn/figures/navbar-setting-0105.png) 里开启工作流才能显示 Workflow 页面。

- 使用工作流需要额外部署 Dag Controller 和{{plato.name}}。详情参见[{{plato.name}}](../..//graph-computing/nebula-analytics.md)和[部署{{explorer.name}}](../deploy-connect/ex-ug-deploy.md)。

- 图查询组件的输入只能是查询语言。

- 图查询组件的结果默认支持保存在 NFS（即本地），也可以保存在 HDFS，方便被多个算法调用。

- 图计算组件的输入可以是{{nebula.name}}或 HDFS 的指定数据，也可以依赖于图查询组件的结果。

  如果依赖于前一个图查询组件的结果，必须和该图查询组件全连接，即该图计算组件的白色输入锚点全都和上一个图查询组件的白色输出锚点连接。

- 部分算法的参数配置也可以依赖于上游节点。

- 图计算组件结果允许保存在 HDFS、{{nebula.name}}中，但是并非所有算法的结果都适合存入到{{nebula.name}}里，在设置**结果保存**页面时，部分算法只能选择 HDFS。

## 算法参数配置说明

请参见[算法简介](../../graph-computing/algorithm-description.md)。
