---
title: 'Conclusion'
tocTitle: 'Conclusion'
description: 'Help automate and extend Storybook'
---

Developers spend [21% of their time](https://www.niss.org/sites/default/files/technicalreports/tr81.pdf) fixing bugs. Tests help reduce the amount of work you have to do by catching defects and speeding up debugging.
But every new feature introduces more UI and states that need tests. The only way to stay productive is to implement an intuitive testing workflow.

Start by writing test cases as stories. You can reuse them in testing tools such as Jest, Chromatic and Axe. Studies suggest that reusing code can shave [42-81% off](https://www.researchgate.net/publication/3188437_Evaluating_Software_Reuse_Alternatives_A_Model_and_Its_Application_to_an_Industrial_Case_Study?ev=publicSearchHeader&_sg=g8WraNGZNGPw0R-1-jGpy0XwUDeAr3qb472J6lhisyQ3l24pSmndO6anMdX2L3HdWHifsczPegR9wjA) dev time.

During development, test while you code to fix obvious bugs. That shortens your feedback loop. It also prevents bugs from hitting production which is [10x](https://ntrs.nasa.gov/search.jsp?R=20100036670) more expensive to fix.

Finally, use a CI server to run all your checks across the entire UI to prevent accidental regressions.

I hope distilling these learnings into a pragmatic workflow helps you implement a solid testing strategy of your own. Let this workflow be your starting point.

## Learn more

The [addon documentation](https://storybook.js.org/docs/react/addons/introduction) offers more guides, code samples and a knowledge base full of recipes.

If you’re coding along with us, your repositories should look like this: [Sample addon repository](http://github.com/chromaui/learnstorybook-addon-code). This example was based on the [Storybook Addon Outline](https://github.com/chromaui/storybook-addon-outline).

You can also reference other addons such as [Pseudo States](https://github.com/chromaui/storybook-addon-pseudo-states), [Dark Mode](https://github.com/hipstersmoothie/storybook-dark-mode) and all [other official addons](https://github.com/storybookjs/storybook/tree/next/addons) and play with them in the [official Storybook](https://next--storybookjs.netlify.app/official-storybook/).

Thanks for learning with us. Subscribe to the Storybook mailing list to get notified when helpful articles and guides like this are published.

<iframe style="height:400px;width:100%;max-width:800px;margin:0px auto;" src="https://upscri.be/d42fc0?as_embed"></iframe>
