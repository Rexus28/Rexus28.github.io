# What does it mean for a machine to know?

Artificial Intelligence learns by finding patterns of information in the data it is given, like when a child learns to recognize animals from images we show them. Eventually, they pick up on the patterns that make a dog a dog: the tail, ears, snoot, and so on.

I trained an [AI to identify different dog breeds](https://mybinder.org/v2/gh/Rexus28/dog-breed-classifier/HEAD?urlpath=%2Fvoila%2Frender%2Fdog_breed_classifier_app.ipynb), and it does reasonably well. It scores an accuracy of about 85%, a solid B. This, and other research, shows that AI can learn patterns from the data, and it gains skill in using what it learns. My AI can take an image of a dog it’s never seen and tell you which breed it most likely is.

Does this mean the AI has knowledge? It makes the correct decisions. It knows a border collie from a Boston terrier. It’s not randomly guessing, otherwise it would only be correct less than 1% of the time. At 85% it’s not right all the time but it’s useful enough. I would say this all counts as knowledge.

However, you and I have a deeper understanding of what a dog is. We can recognize cartoon dogs from real dogs. Unfortunately, my AI can’t do any of that, and it didn’t show any of its work on the test either, so it only gets partial credit. 

Artificial Intelligence can’t explain to you why it made a decision. It merely recognizes patterns and chooses among the options it’s seen before. It uses a lot of math, and if I want to know why my AI made its decision I could delve into that math to gain some insights. But this is more interrogation than explanation.

This is a huge problem with AI. Not that it can’t learn, but that it can’t explain what it’s learned or why it believes what it does. It can learn that dogs have floppy ears or that wolves have pointy faces, and it can do well telling them apart. And in fact the researchers from the University of Washington made such an [AI identifying wolves from huskies](https://arxiv.org/pdf/1602.04938.pdf), however, they intentionally trained it poorly, using only images of wolves only on snow and huskies on grass. Afterwards, they interrogated it and found out it identified wolves by the snow in the background.

Because it couldn’t explain its decisions, it never really learned the difference between wolves and huskies. It didn’t gain any knowledge, just something that looked like it. That’s why we justify knowledge by explaining it. And researchers need to figure this out, so they can justify that AI is making the right decisions. This is not the fault of the AI, it doesn’t know any better. This is up to the humans (myself included) who are improving the technology.


## References
@inproceedings{ribeiro2016should,
  title={" Why should i trust you?" Explaining the predictions of any classifier},
  author={Ribeiro, Marco Tulio and Singh, Sameer and Guestrin, Carlos},
  booktitle={Proceedings of the 22nd ACM SIGKDD international conference on knowledge discovery and data mining},
  pages={1135--1144},
  year={2016}
}

