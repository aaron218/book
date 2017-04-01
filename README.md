# book

本知识库是公开的知识整理和数据收集仓库，是与GitHub关联的GitBook.

[另一个知识库](https://newstring.myqnapcloud.com:8081/dokuwiki/) \(此知识库部署在个人服务器上，不保证实时的可用性，亦不保证内容的完整性，主要用于知识点的第一步收集以及备忘工作，并且有账户管理\)

# 备忘

以下内容均为个人的备忘，关于markdown与编辑，与book的实际内容无关

## 关于Gitbook的编辑

**!!!不建议使用GitBookEditor!!!**

GitBook是可以通过WebHook来与Github进行同步的，因此，不仅可以通过GitBookEditor进行编辑，可以使用其他的md编辑器以及代码编辑器进行编辑并管理。

**但是要特别注意的是，WebHook默认情况下可以感知github的变化并同步到gitbook上，但是反之则不行\(暂时未找到方案\)**

所以，在编辑GitBook的时候，要特别关注这一点，**不要在GitBookEditor上进行同步操作**。以免出现版本的不一致。甚至，也不建议使用GitBookEditor，不仅仅在于暂时还不稳定，同时也存在包括突然退出而丢失未保存的数据\(然而随时保存也会产生版本过多的问题\)等大量不便于集中注意力到生产内容上的问题。

### 文件同步

* 当使用GitBookEditor进行编辑的时候，切记每一次的SAVE操作，实际上都是进行了一次Commit。所以如果book是与github绑定的，可能会造成github上存在大量的提交\(一定程度上会造成仓库变大\)
* 如果GitBook是与GitHub关联的，那么最好所有的提交操作都通过github来进行，方法是，先clone book所在的仓库，然后gitbookEditor在仓库所在的目录下进行编辑。一般只进行SAVE操作而不进行同步，如果不慎进行了一次同步，则及时的将变更提交到GitHub上以补救，否则可能在几个版本以后，两边的文件无法直接的进行合并。
* 对于多媒体文件的引入，一般建议尽量在通用的编辑工具下完成，以免代入错误的引用路径。规范的路径则需要参照gitbookEditor自动生成的部分

### 数据冲突

无论怎样控制，数据冲突都可以认为是难以避免的。当出现这样的情况，首先考虑通过版本工具进行数据的合并，如果无法合并，则观察冲突文件，看能否手动合并。当这些方法都不可行或者都难以满足需要，则以Github上的版本为准进行合并\(如果是关联github的话\)。

## 章节组织

对于非书籍类型的gitbook\(如notebook类型\)。一般来说每一个文件代表了一个主题，主题内通过H1——H3的层级控制内容级别。Summary中第一级是一个领域，第二级是一个切面或者一个主题，第三级是一个基于第二级展开的主题，一般不需要第三级。

# markdown使用

由于不建议使用GitBookEditor，所以一般应用与工具的关系如下：

* 纯文本编辑：任意文本编辑工具或者Intellij或者MarkdownPad
* 含特殊功能：包含了插件才能提供的功能，如数学公式等，这里建议使用GitBookEditor进行实验性编辑，并通过它导入相应插件，然后再到其他的编辑器中完成具体的编写\(以保证相应的插件与展现的一致性\)。

## code

* java code
  ```java
  public ServiceRequest setParam(Map<String, Object> param) {
      this.param = param;
      return this;
  }
  ```

## Math



