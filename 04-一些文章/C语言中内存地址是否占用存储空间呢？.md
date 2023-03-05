# C语言中内存地址是否占用存储空间呢？

> https://www.zhihu.com/question/53895024

1.[内存地址](https://www.zhihu.com/search?q=%E5%86%85%E5%AD%98%E5%9C%B0%E5%9D%80&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)要不要占据内存空间？

这里有一个非常重要的关键点，那就是显示器。显示器具有很大的迷惑性，他会让你产生错觉，认为代码是你写出来的。

其实你用脚想一想，显示器上面的字是你写的么？代码真的是你打出来的？你用笔在上面写字，还是用刀刻，使显示器出现字？

而且，显示器对于计算机来讲并不是必要的。

所以，你所看的一切都是假的，人们真正所做的事情，就是[敲击键盘](https://www.zhihu.com/search?q=%E6%95%B2%E5%87%BB%E9%94%AE%E7%9B%98&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)，或者点击鼠标。

当你敲键盘，点鼠标的时候，会产生一道道微弱的电流，会稍微改变计算机电路里面的部分电压。计算机里面的一切，都是以电压的形式存在。而显示器唯一的作用，就是通过层层抽象，把电压的变换抽象出来，变成代码让你看到。

内存也是一坨庞杂无比的电路。经过层层抽象，最终才会显示出来几个[16进制数](https://www.zhihu.com/search?q=16%E8%BF%9B%E5%88%B6%E6%95%B0&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)供你操控。每个16进制位，都代表4根线。0028FFEC有8个16进制位，意味着这是一个32位的计算机。这意味着地址的变化会改变32根线的电压。这也是你通过键盘的按压实现的。

可是这个和地址占不占据空间有什么关系呢？

其实你的问题应该稍微修改一下，最好分裂成文两个。

第一个，显示器上面出现的代码和地址到底占不占空间？

回答：显示器上面出现的任何东西都会占据空间。只要是你通过键盘打的字，都会占据空间。

第二个，内存地址到底是什么？

回答：你用[c语言](https://www.zhihu.com/search?q=c%E8%AF%AD%E8%A8%80&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)写程序的时候，左边会有12345678...的行号，尤其是你写大程序和调试的时候。[行号](https://www.zhihu.com/search?q=%E8%A1%8C%E5%8F%B7&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)是很重要的。它能帮你精确的定位。

如果把内存想象成为篇巨长的程序，或者一篇巨长的文章。那么内存地址就是相当于行号之类的东西。

然而对于计算机来讲，就是通过真实的[线路](https://www.zhihu.com/search?q=%E7%BA%BF%E8%B7%AF&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)来操控地址的。32位的计算机意味着它有32根线，任意改变，计算机就会根据电压变化重新定位到一个内存。

\2. 计算机怎么识别内存地址？

计算机根本就不需要识别内存地址。它是由硬件电路实现的。就像[发电厂](https://www.zhihu.com/search?q=%E5%8F%91%E7%94%B5%E5%8E%82&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)发的电点亮了你家电灯一样。是因为你家的电灯的电路连接了发电厂的电路，而不是因为发电机能够自动识别你家地址。

也就是说，内存地址是人类从电路里面抽象出来的给人识别的，而不是给机器识别的。

它本质上是一个[数据选择器](https://www.zhihu.com/search?q=%E6%95%B0%E6%8D%AE%E9%80%89%E6%8B%A9%E5%99%A8&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)。内存地址在机器看来就是一堆选择线。

也就是说，虽然发电机已经连接了你家的电灯，但是你依然需要合上你家门口的闸刀，来让电路导通。这样你家的电灯才会亮。

如果我们对家门口的[闸刀](https://www.zhihu.com/search?q=%E9%97%B8%E5%88%80&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)进行编码，假设0为断开状态，1为合上状态。假设有八户人家。我们输入00000001（手动扳开关），这时候就有一户人家的灯是点亮的。输入00100010（手动去人家门口扳闸刀），就会有两户人家的灯是亮的。但是你能说，是因为[发电机](https://www.zhihu.com/search?q=%E5%8F%91%E7%94%B5%E6%9C%BA&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)能够识别人家的地址吗？

我们对计算机输入地址（比如FF0062BC）的时候本质上也是一样的，它会使用[二进制的](https://www.zhihu.com/search?q=%E4%BA%8C%E8%BF%9B%E5%88%B6%E7%9A%84&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)形式存在内存里面。而内存中的数据实际上是通过[电信号](https://www.zhihu.com/search?q=%E7%94%B5%E4%BF%A1%E5%8F%B7&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)的方式存储的（也就是说，在内存里面，0就是一段[低电平](https://www.zhihu.com/search?q=%E4%BD%8E%E7%94%B5%E5%B9%B3&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A137054697%7D)的导线，1就是一段高电平的导线）。

**你可以想象成为，内存里面有许许多多的闸刀，当你输入一个地址，他就会自动改变电信号，扳动内存里面的闸刀，使得其中一些导线可以被使用。**

计算机只是提前连接好了所有的线路，你可以直接想象你输入地址就是扳动了内存里面的开关，让里面的的一部分数据可以使用。（就和扳动开关那一家的灯就能使用的原理是一样的）