# Searching
[程序设计包容性红黑榜 - 大家的板块 / 网络黄页 - 小众软件官方论坛](https://meta.appinn.net/t/topic/45697/4?u=chaoses_ib)

> 这个题目我第一想到的是各个程序的搜索功能，如果不是汉语母语开发者开发的，很少能够支持拼音搜索，有的即使支持了也不支持多音字。
> 
> 这个问题的直接原因是，基于英语的键盘布局在输入任何字元比英语多的语言时都需要对字元进行编码，而像中文这种字元非常多的情况，很难找到一种容易学习的编码方式，最终靠部分编码和交互确认的输入法通过牺牲输入效率降低了学习难度，成为了主流。许多语言并不需要使用这种输入法，于是开发者不要说支持，很可能根本没想到过还会有这种事情；即使有用户反馈，因为设计完善处理的算法比较困难，可能也会不了了之。
> 
> 更本质地来看，这实际上不只是中文输入法的问题，而是用于搜索的输入与用于显示的输入之间是不对等的。我会在给文件命名时打一长串拼音来输入准确的汉字，因为一个文件名显示的次数要远多于编辑它的次数，通过输入汉字来提高视觉识别效率是划得来的；而在搜索时，输入只会被使用一次，也很少用于显示，输入汉字没有直接输入拼音划算。这样来看，就不止中文有这样的问题，许多其它语言也有：
> * "Brontë" is six characters that should look like "Bronte", but with double-dots on the "e" character.
> * "Résumé" is six characters that should look like "Resume", but with /-shaped accents on the "e" characters.
> * "læti" should be *four* letters long-- the second letter should not be two letters "ae", but should be a single letter that looks like an "a" entirely fused with an "e".
> * "χρονος" is six Greek characters that should look kind of like: xpovoc
> * "КАК ВАС ЗОВУТ" is three short Russian words that should look a lot like: KAK BAC 3OBYT
> * "ടധ" is two Malayalam characters that should look like: sw
> * "Ｈｅｌｌｏ" is five characters that should look like: Hello
> * emoji 字符，例如“😇”的 CLDR 短名称是“smiling face with halo”
> 
> [Text::Unidecode](https://metacpan.org/pod/Text::Unidecode) 是一个用于将 Unicode 文本以人类可读的方式转换为 ASCII 文本（从键盘上能够直接输入的文本）的库，这个库在一定程度上能够解决上面的问题，但因为一个字符只能有一种对应 ASCII 表示，并不是很适合用于搜索，也无法支持多音字。不过即使它为一个字符提供了多种 ASCII 表示，搜索效果也还是比较局限，用户需要猜到准确的关键字才能搜到。NLP 中的语义搜索可以做到按语义进行模糊搜索，但在短查询上的准确性又可能不如关键字搜索。设计一种混合算法，对短查询倾向于关键字匹配，对中等查询倾向于通过编辑距离等度量实现的机械模糊匹配，对长查询倾向于语义匹配，可能是完美的解决方案。不过想让各种应用普及这种搜索，恐怕只有 Apple 生态有可能做到了。对于其它生态来说，等 AGI 实现可能还更现实些。