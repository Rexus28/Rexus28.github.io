# What I've Learned from Using PyTorch-Lightning and Hydra
### or, How I've Learned to Embrace Modular Code

## My Past Mistakes
This post is about my experience learning [PyTorch-Lightning][1] and [Hydra][2]
over the past few months. I've been using the regular version of PyTorch for
the past two years, but adopting these two new packages has shifted the way I
work and write code.

My background is not in computer science or software development, but I have
been using Python for nearly 10 years, including machine learning and data
science research over the past 2 years. It's been a journey of learning best
practices on my own. I've known that writing code to be modular is better for
reusability, but this usually involved me separating steps of whatever process
I was coding in computational order. In hindsight it was more extracting via
functions to avoid over-nesting, which was good, but wasn't enough when
projects starting getting bigger.

Most of my prior PyTorch projects started from simple examples, then I slowly
added more and more to it without much of a plan for organization. This
resulted in coupling of the models, data, and training loops, such that making
changes later on was difficult and it was hard for anyone else to read and use
the code. Another pain that I ran into was adding a new variable for the
command line interface (CLI) and having to cascade it through multiple
functions to get to where it was used.

## PyTorch-Lightning
I slowly found ways to better organize PyTorch code, but discovering
PyTorch-Lightning made a huge difference. It provides a framework for
abstracting model and data into classes that better separate their
responsibilities. It also provides a class for the training loop that covers
all the boilerplate code from regular PyTorch that is required to loop through
the data, calculate the gradient, and then update weights.

Besides helping to visually organize the model and data classes for
readability, it makes updating easier because you know where to look and you
can easily swap out models and data with minimal impact to the rest of your
code, and most importantly, to the model training process. Changing model
architectures is as easy as instantiating a new object and telling the trainer
to fit it on the data.

## Hydra
There are still a lot of different settings to be managed for any deep learning
project, and with all of the settings for the PyTorch-Lightning trainer, there
are more to keep track off. Luckily, the Hydra package offers a way to pull
them all out of the code itself. Now, you may be wondering why this is
desirable. With specified configuration files, we know exactly where to look to
see settings and hyperparamers, and without hunting through the code we get a
better top level view. We also don't need to alter any part of the code to
change how it runs.

But, the best part is that Hydra allows you to instantiate objects based
entirely on its configuration by including a path for the target class to
create. This means that the code doesn't need to know which specific model or
data class it needs to create. We can now remove any logic or passing of
arguments for specific classes. So, swapping models or datamodules only
requires the class in the project directory and that we give it a yaml file for
settings. In a detailed [template from ashleve on GitHub][6], and in a [simple
template][7] that I made, you can see that the `train.py` file only references
the model, datamodule, and trainer sections of the configuration. Regardless of
the values, there is no change in the logic if we swap out different models,
data, or trainer settings.

## Takeaways
Creating good modular code, which separates responsibilities well and creates a
generic interface for all parameters, allows for easy updates and moving parts
around. This makes adapting code for new situations, just trying out different
experiments, or moving what worked into a new project effortless. It does
require some extra effort up front, but the open source tools and templates
available make it easy to adopt these best practices from the start, or even
after you've developed most of your project already.

It's really the open source community's devotion to best practices that have
helped me learn how to craft better modular code. To see how it should be done
and allowing me to create my own version to learn the process and share with
others. Certainly, without finding these libraries I would not have learned as
much as I have.

## References
1. Lightning AI [Welcome to PyTorch Lightning][1]

2. Meta Platforms, Inc [Hydra - Getting Started][2]

3. Arjan, [Configuration Management For Data Science Made Easy With Hydra
(video)][3], ArjanCodes, *YouTube*

4. Przemyslaw Joniak, [Boost your AI research with hydra+Lightning
templates][4], *LeapMind Tech Blog*

5. Lightning-AI, [deep-learning-project-template][5], *GitHub*

6. ashleve, [lightning-hydra-template][6], *GitHub*

7. Daniel Sobien, [hydra-deep-learning-example][7], Rexus28 on *GitHub*

[1]: https://pytorch-lightning.readthedocs.io/en/stable/
[2]: https://hydra.cc/docs/intro/
[3]: https://youtu.be/tEsPyYnzt8s
[4]: https://techblog.leapmind.io/blog/boost-your-ai-research-with-hydra-and-lightning-templates/
[5]: https://github.com/Lightning-AI/deep-learning-project-template
[6]: https://github.com/ashleve/lightning-hydra-template
[7]: https://github.com/Rexus28/hydra-deep-learning-example
