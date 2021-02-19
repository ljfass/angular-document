# 记录angular官方文档阅读笔记

## 1. 
### NgModule：Angular 的基本构造块，为组件提供了编译的上下文环境。NgModule 会把相关的代码收集到一些功能集中。应用至少会有一个引导应用的根模块，通常还会有很多特性模块。 
## 2. 
### 模块、组件和服务都是使用装饰器的类，这些装饰器会标出它们的类型并提供元数据，以告知 Angular 该如何使用它们。
    · 组件类的元数据将组件类和一个用来定义视图的模板关联起来。模板把普通的 HTML 和 Angular 指令与绑定标记（markup）组合起来，这样 Angular 就可以在渲染 HTML 之前先修改这些 HTML。  
    · 服务类的元数据提供了一些信息，Angular 要用这些信息来让组件可以通过依赖注入（DI）使用该服务。  
## 3.  
### NgModule简介  
### 每个 Angular 应用都至少有一个 NgModule 类，也就是根模块，它习惯上命名为 AppModule，并位于一个名叫 app.module.ts 的文件中。引导这个根模块就可以启动你的应用。  
### @NgModule 元数据  
    · declarations（可声明对象表）-- 那些属于本 NgModule 的组件、指令、管道。  
    · exports（导出表）-- 那些能在其他模块的组件模板中使用的可声明对象子集。  
    · imports（导入表）-- 那些导出了本模块中的组件模板所需的类的其他模块。
    · providers -- 本模块向全局服务中贡献的那些服务的创建器。这些服务能被本应用中的任何部分使用。（你也可以在组件级别指定服务提供者，这通常是首选方式。）  
    · bootstrap -- 应用的主视图，称为根组件。它是应用中所有其他视图的宿主。只有根模块才应该设置这个 bootstrap 属性。  
## 4.  
### 通过根模块启动应用  
### NgModule 用于描述应用的各个部分如何组织在一起。每个应用有至少一个 Angular 模块，根模块就是你用来启动此应用的模块。按照惯例，它通常命名为 AppModule。  
### imports 数组  
#### 模块的 imports 数组只会出现在 @NgModule 元数据对象中。它告诉 Angular 该模块想要正常工作，还需要哪些模块。  
### providers 数组
#### providers 数组中列出了该应用所需的服务。当直接把服务列在这里时，它们是全应用范围的。当你使用特性模块和惰性模块时，它们是范围化的。   
## 5.常用 Angular 模块  
### BrowserModule 
### CommonModule 
### FormsModule 
### ReactiveFormsModule 
### RouterModule 
### HttpClientModule  
### 对于运行在浏览器中的应用来说，都必须在根模块中 AppMoodule 导入 BrowserModule,因为它提供了启动和运行浏览器应用时某些必须的服务。BrowserModule 的提供者是面向整个应用的，所以它只能在根模块中使用，而不是特性模块。特性模块只需要 CommonModule 中的常用指令，它们不需要重新安装所有全应用级的服务。  
### 如果你把 BrowserModule 导入了惰性加载的特性模块中，Angular 就会返回一个错误，并告诉你要改用 CommonModule。
