---
layout: article
title: About
key: page-about
---

Under construction.

{% highlight c++ %}
static f32 acc = 0.0f;
acc += 0.005f;
f32 r = 0.75f + 0.25f * FSin(acc);
c4f clearColor = { r, 0.8f, 1.0f, 1.0f };
graphics->commandList->ClearRenderTargetView(cdh, (f32*)&clearColor, 0, nullptr);
{% endhighlight %}
