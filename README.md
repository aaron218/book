<span id="jump"></span>
# book
本知识库是公开的知识整理和数据收集仓库，是与GitHub关联的GitBook.


更新的以及范围更广的内容 保存在(受限访问环境): [AXON](https://newstring.myqnapcloud.com:8081/dokuwiki/doku.php 个人知识库，服务器不保证全天候可用)


所有观点均会随着认知和外围系统环境的变化而发生变化

>不断迭代，永无止境


# 备忘
以下内容均为个人的备忘，关于markdown与编辑，与book的实际内容无关

## 关于Gitbook的编辑 备忘

只有SUMMARY.md下声明的文件才会编译 二次引用的文件并不能直接编译，除非在SUMMARY中也申明一次

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

使用
   ```html
    <span id="jump"></span>
    和 [TOP](#jump) 以及 [回到首页](../README.md#jump)等方式实现页内和页间跳转
   ```
但是仅在gitbook上有效

# markdown使用

由于不建议使用GitBookEditor，所以一般应用与工具的关系如下：

* 纯文本编辑：任意文本编辑工具或者Intellij或者MarkdownPad
* 含特殊功能：包含了插件才能提供的功能，如数学公式等，这里建议使用GitBookEditor进行实验性编辑，并通过它导入相应插件，然后再到其他的编辑器中完成具体的编写\(以保证相应的插件与展现的一致性\)。

## code

* java code
  ```java
    public class BubbleSort
    {
        public void sort(int[] a)
        {
            int temp = 0;
            for (int i = a.length - 1; i > 0; --i)
            {
                for (int j = 0; j < i; ++j)
                {
                    if (a[j + 1] < a[j])
                    {
                        temp = a[j];
                        a[j] = a[j + 1];
                        a[j + 1] = temp;
                    }
                }
            }
        }
    }
  ```
  
* C code

  ``` c
    #include <stdio.h>
    #define SIZE 8
     
    void bubble_sort(int a[], int n);
     
    void bubble_sort(int a[], int n)
    {
        int i, j, temp;
        for (j = 0; j < n - 1; j++)
            for (i = 0; i < n - 1 - j; i++)
            {
                if(a[i] > a[i + 1])
                {
                    temp = a[i];
                    a[i] = a[i + 1];
                    a[i + 1] = temp;
                }
            }
    }
  ```

* javascript
    ```javascript
    function bubbleSort(arr) {
        var i = arr.length, j;
        var tempExchangVal;
        while (i > 0) {
            for (j = 0; j < i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    tempExchangVal = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = tempExchangVal;
                }
            }
            i--;
        }
        return arr;
    }
    ```
    
    
* python
    ```python
    def bubble(bubbleList):
        listLength = len(bubbleList)
        while listLength > 0:
            for i in range(listLength - 1):
                if bubbleList[i] > bubbleList[i+1]:
                    bubbleList[i] = bubbleList[i] + bubbleList[i+1]
                    bubbleList[i+1] = bubbleList[i] - bubbleList[i+1]
                    bubbleList[i] = bubbleList[i] - bubbleList[i+1]
            listLength -= 1
        print bubbleList
    ```
* Golang    
    ```go
    package main  //main函数
    import "fmt"  //相当于#include
    func main() {
        ar := [10]int{9, 8, 6, 4, 2, 7, 1, 3, 0, 5}
        num := len(ar)      //:=自动匹配变量类型
        for i := 0; i < num; i++ {       //花括号{必须在这一行 if也一样
            for j := i + 1; j < num; j++ {
                if ar[i] < ar[j] {
                    ar[i], ar[j] = ar[j], ar[i] //相比某语言不需要临时交换变量
                }
            }
        }
        fmt.Println(ar)
    }
    ```
## Math



[TOP](#jump)
