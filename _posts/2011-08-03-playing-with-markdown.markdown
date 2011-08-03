---
layout: post
title: Trying out Markdown
status: publish
published: true
meta: {}
---

# Very cool header

## An even cooler header

Trying to look at using markdown and vim together...

### Header 3
> What the dog saw

Things VIM is good at:

* Lists
* Other Stuff

Trying an image:
![GO GREEN](/images/vim-shot.png "getting green")


Here's a post in cucumber - this isn't the nicest highlighting...

{% highlight cucumber linenos %}
Feature: Manage pomodori
  In order to [goal]
  [stakeholder]
  wants [behaviour]
  
  # test comment
  Scenario: Register new pomodori
    Given I am on the new pomodori page
    And I press "Create"
{% endhighlight %}

And here's a ruby post.  not the nicest...

{% highlight ruby linenos %}
class Account
  # what's up, fool?
  def init
  end
end
{% endhighlight %}

