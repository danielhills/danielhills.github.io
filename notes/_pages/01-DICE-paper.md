# Disentangling User Interest and Conformity for Recommendation with Causal Embedding (DICE)

__Date read:__ 13/04/2021

__Paper:__ https://arxiv.org/pdf/2006.11011.pdf

Aims to separate out user ‘conformity’ from interest. The motivation being that recommendation models suffer popularity bias, which you can account for (with weightings etc.), but that doesn’t separate out who is consuming something based on conformity or because of genuine interest.

DICE - Disentangling Interest and Conformity with Causal Embedding.

Term to remember: IID - Independent and identically distributed random variables.

I haven’t read the paper in detail and whilst the methodology is complicated, from my understanding the approach comes down to one key feature, which is splitting the data out into conformity and interest driven clicks.

For example, consider you have item A and B shown to a user. A is more popular in general than B, then if:
- A picked over B - we can’t be sure whether click comes from conformity or interest, but we can say that `Ca + Ia > Cb + Ib` as well as `Ca > Cb`
- B picked over A - here we can be more confident that the click is from interest, so `Cb + Ib > Ca + Ia`, whilst `Ca > Cb` still remains and we also now know that `Ib > Ia`

`C` - conformity
`I` - interest

The data is split out based on the above, then trained separately and the combined loss is optimised together. Based on their testing at least, it seems to work very well, but I think the main interest seems to be it teasing out actual interest which makes it more generalisable and interesting for post recommendation model analysis.
