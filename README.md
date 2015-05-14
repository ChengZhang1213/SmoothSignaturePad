# **Smooth Signature Pad** #
----------
depends on project,[android-signaturepad](https://github.com/gcacace/android-signaturepad).

----------

**主要改变**

   删减了signaturepa中的一些不需要使用的类，在显示方面，添加了一个dialog,可以在dialog上面手写文字并保存在Gellery.


**技术要点**

smooth 的实现主要使用的是[贝塞尔曲线(Bézier curve)](http://bbs.csdn.net/topics/390358020)。如果不使用曲线算法，我们会发现，虽然处理过脏数据的图片相比于未做任何处理的方式锯齿要少一些，但是可以看出还是有一定的锯齿，签名出来的不是很美观，这一点可以看[Eric Burke](https://corner.squareup.com/2010/07/smooth-signatures.html)的一篇博客，看出的效果是未做Bézier处理的。
因此核心类为Utils包下的Bezier类以及SignatureView。
