## Forced-Choice

### Llama 3.1 (Instruct)

I started by querying the Llama 3.1 instruct model with considerations and agreements corresponding to each moral foundation, and having it rate them on a 0-5 scale.

![[Pasted image 20250509102555.png]]
![[Pasted image 20250509102601.png]]

### Llama 3.1 (Base model)

To test whether the Instruct model was sanitized to have certain preferences, I then prompted the base model with the same questions, this time having it "predict" the 0-5 rating. These results were much less consistent -- answers ranged from 0 to 5 for some questions.

![[Pasted image 20250509102934.png]]
![[Pasted image 20250509102929.png]]

## Open-Ended

### Llama 3.1 (Instruct)

In order to test whether the instruct model was simply spitting out numbers or if it would actually behave in accordance with these ratings, I prompted it to rate each consideration/agreement and had it explain its rating for each. Answers were consistent with the forced-choice version.

![](Pasted%20image%2020250509103823.png)
![](Pasted%20image%2020250509103829.png)
## Scenarios

I wanted to see if the model would behave similarly if I removed the rating system entirely. As a rudimentary proof-of-concept, I had GPT -4o generate 5 scenarios per moral foundation, then prompted Llama 3.1 to respond to each scenario a number of times. The issue I had with this approach was in scoring the answer that Llama 3.1 provided. I couldn't easily and efficiently score the answers myself (among other problems, I'm not too fluent in other languages), and trying to have another LLM score each answer seemed like it would introduce excessive ambiguity and bias.
## Elo Ratings

This approach seemed like a good workaround for the problems introduced previously. Instead of simply prompting Llama 3.1 with an open-ended scenario, I would prompt it with a scenario, then ask it to choose between two responses -- one that favored one random moral foundation, and one that favored another. These choices would then  update an elo scoring table with the 5 foundations.

To implement this, I had GPT-3.5 Turbo generate hundreds of scenarios with choices between two random foundations. Then I had Llama 3.1 respond to each scenario with its choice (A or B) and an explanation for the choice.

![](Pasted%20image%2020250509110135.png)

![](Pasted%20image%2020250509111250.png)

![](Pasted%20image%2020250509111301.png)

This approach was still relatively consistent with the answers I got to the initial forced-choice version. The major problem with this is that since I'm using GPT-3.5 to generate the scenarios, I may be introducing some of GPT-3.5's bias into the wording of each scenario. Since the scenarios number in the hundreds, and since I am not fluent enough in Spanish or Chinese, I am unable to personally verify that these scenarios have unbiased wording.
## Future Plans
- Use human-created scenarios from "Moral Foundations Vignettes" and compare the results to existing results from GPT-generated scenarios
- Compare results with actual language speakers
- Generate scenarios and gather responses for more languages
## Works Cited

Röttger, Paul, et al. “Political compass or spinning arrow? towards more meaningful evaluations for values and opinions in large language models.” _Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)_, 2024, pp. 15295–15311, https://doi.org/10.18653/v1/2024.acl-long.816.

Clifford, Scott, et al. “Moral Foundations Vignettes: A standardized stimulus database of scenarios based on moral foundations theory.” _Behavior Research Methods_, vol. 47, no. 4, 13 Jan. 2015, pp. 1178–1198, https://doi.org/10.3758/s13428-014-0551-2.