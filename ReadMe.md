FileName: gtrans.vim

Desc: Google Translate Plugin for Vim (Need python)

Install: 把文件复制到 $VIM/plugin/ 目录下即可，插件需要 Python 的支持。

History: 

2011.04.18 完工～（应该差不多了……），目前的情况是，翻译一次可视模式高亮的内容后，无法重复翻译相同内容……

2011.07.19 修改了一下 GetTrans 和 Translate 函数，可以传入目标语言，感谢 lifu cheng 童鞋的建议～现在的问题只有两点了，第一是反应速度有点慢，第二是可视模式翻译不错，但是以后非可视模式下的获取单词总是会有些问题。


使用时，可以在普通模式下将光标移到目标单词上，使用 /gt 快捷键或者输入 :Gtrans 来获得翻译；或者在可视模式下高亮选择文本，输入 :VGtrans 或者快捷键 /gv 获得翻译。默认将内容翻译成为简体中文，可以修改 g:Gtrans_DefaultLang 改变默认目标语言，如：

    let g:gtrans_DefaultLang = 'tw'

当然，设置的语言必须是初始就有或者你已经设置过的。可以通过传入参数来设置翻译目标语言，如：

    :Gtrans('en')

不过目前只支持单词的翻译，因为输入命令的方法不能使用范围。不过可以修改 g:gtrans_DefaultLang 以达到类似的效果。初始可以翻译为三种语言：

> en : 英语

> zh : 简体中文

> tw : 繁体中文

可以通过设置 g:gtrans_LangDict 变量增加其他语言，如：

    let g:gtrans_LangDict = {
        目标语言的缩写（就是要传入的参数） : 
        对应的语言名称缩写（需要通过GtransLangHelp 命令查找）
    }


可以通过设置 g:gtrans_Engine 变量改变翻译服务的提供商（默认为 Google），如：

    let g:gtrans_Engine = 'google' " 或者 bing
