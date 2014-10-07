---
layout: post
title:  "Python, pip, virtualenv environment via MacPorts"
date:   2014-10-06
categories: OS X, Python
---
During the course of my day job, I needed to install Python and pip. For those using MacPorts, below is the method I've used to accomplish the task. I used Python v2.7 since I hear v3 has some backward compatibility issues.

For each component, I perform a `search`, `install`, `select --list` and then `select --set`.

# Python

## Search available Python versions

{% highlight bash %}
sudo port search python2*
{% endhighlight %}

## Install Python v2.7.8

From the list of Pythons that show up, I chose to install python27:

{% highlight bash %}
sudo port install python27
{% endhighlight %}

## List installed Pythons

{% highlight bash %}
sudo port select --list python
{% endhighlight %}

A number of Apple installations should show up along with the Python that was installed in the last step (python27)

## Set active Python version

Set the MacPorts Python 2.7.x installation as the default Python system-wide:

{% highlight bash %}
sudo port select --set python python27
{% endhighlight %}

# pip

## Search available pip versions:

{% highlight bash %}
sudo port search py*-pip
{% endhighlight %}

## Install pip v1.5.6

{% highlight bash %}
sudo port install py27-pip
{% endhighlight %}

## List installed pips

{% highlight bash %}
sudo port select --list pip
{% endhighlight %}

**Note:** If you get an error executing the above, try forcing the activation by executing `sudo port -f activate py27-pip`

## Set active pip version

{% highlight bash %}
sudo port select --set pip pip27
{% endhighlight %}

# virtualenv

## Search available Python virtual environments

{% highlight bash %}
sudo port search py*-virtualenv
{% endhighlight %}

## List installed virtualenvs

{% highlight bash %}
sudo port select --list virtualenv
{% endhighlight %}

## Install virtualenv 1.11.6 for Python v2.7

{% highlight bash %}
sudo port install py27-virtualenv
{% endhighlight %}

## List installed virtualenvs

{% highlight bash %}
sudo port select --list virtualenv
{% endhighlight %}


## Set active virtualenv
{% highlight bash %}
sudo port select --set virtualenv virtualenv27
{% endhighlight %}

Following the above should give you Python, pip and virtualenv for Python 2.7. As a bonus, MacPorts also ensures there's an `easy_install` version that's specific to your MacPorts Python installation. In the above case, it should be located in `<MacPorts_Home>/bin/easy_install-2.7`. If you can't remember the location of your MacPorts home directory, you can use bash completion by having it complete `easy_install`.