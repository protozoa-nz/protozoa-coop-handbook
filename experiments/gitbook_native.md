# Gitbook Native

## The problem

We were talking with a prospective client and they proposed a unique challenge:
- an offline resources that can be installed as an app (android + iOS)
- NGO fundraised budget ( < $10K ?)
- desire to internationalise content


## Possible solution

We wanted an easy online content editor... which could be folded into an app.
The original client is still finalising plans, but in the meantime we ran this small test.

Out of curiosity we built a mock up app that combined 2 existing tools :
- [Gitbook](www.gitbook.com) - an excellent online markdown editor, the tech behind this handbook even!
- [React Native](www.reactnative.com) - an emerging javascript framework which makes it easy to build phone apps

We used a small piece of [bridging tech](https://www.npmjs.com/package/react-native-htmlview) to convert markdown into react-native code.

![](https://github.com/protozoa-nz/gitbookNative/raw/master/logo.png)

repo: https://github.com/protozoa-nz/gitbookNative


## Where next

The initial experiment is incredibly promising - it looks like we can make it easy for lots of communities to make resources offline friendly with very little resources.
This is particularly powerful for educational materials and locations where mobile data is expensive.

If you're interested in seeing more of this, please feel free to extend the code we've already written. If you'd like this for you community and have funding to work more on this, we'd also love to hear from you.

We're likely going to revisit this when we have a couple of paying contracts sorted.
 
