+++
title = "Projects"
slug = "projects"
+++

## PII Remediation Evaluation for LLM Pretraining

The [BLOOM](https://bigscience.huggingface.co/blog/bloom) large language model (LLM) is the cumulation of BigScience, a one-year collaborative research workshop involving over 1,000 researchers. It was trained in [complete transparency](https://bigscience.notion.site/BigScience-214dc9a8c1434d7bbcddb391c383922a), has 176B parameters, and generates text in 46 languages. For most of these languages, BLOOM will be the first language model ever created with over 100B parameters.

As LLMs are known to [memorize instances of the training data](https://arxiv.org/abs/2012.07805), such undertakings require the careful treatment of Personally Identifiable Information (PII). The [Personal Identifiable Information Standard (PIISA)](https://github.com/piisa/piisa) has worked concurrently with BigScience to develop data governance and create a PII remediation framework that complies with data standards across global jurisdictions.

As part of this framework, a remediation pipeline, [Muliwai](https://github.com/piisa/piisa/blob/main/docs/specs.md), is being developed to handle numerous data formats across over 200 languages. In this project, we are currently developing an experimental pipeline to test Muliwai's application to language modeling, and evaluate its effects on LLMs trained after remediation.

---

## Drug Repurposing for Leishmaniasis Using a GNN Approach

Leishmaniasis is a neglected parasitic disease affecting remote and poor areas. Thus, many potential treatments for leishmaniasis are unavailable, unaffordable, or lead to adverse effects for the majority of affected inviduals. Due to the limited research and development resources allocated to neglected diseases, drug repurposing is an attractive and cost-effective method for developing new treatments.
Here, we develop the first drug repurposing model for leishmaniasis based on Hyperbolic Graph Neural Networks (HGNNs).

<!-- {{< rawhtml >}}
<p style="text-align:center;">
<img src="/images/projects/hgnn-leishmaniasis.png" width="75%"/>
</p>
{{< /rawhtml >}}

Our model leverages protein-drug interactions across *Leishmania major* and two other eukaryotic parasites, *Plasmodium falciparum* and *Trypanosoma brucei*.
By utilizing the interactions of candidate drugs with other parasites, we create a larger training dataset and allow our model to learn better drug representations.

By comparing our HGNN model against standard GNN architectures in Euclidean space, we found that embedding protein-drug interaction networks using hyperbolic geometry is advantageous for drug repurposing.
We also see a significant performance gain for our approach over machine learning models that rely on protein or drug features alone.

Finally, we use our model to predict protein-drug interactions that could be exploited, either as a booster to increase the therapeutic effect of an existing anti-leishmaniasis drug, or as a novel chemotherapeutic treatment against the disease. -->

---

## Short and Sparse Deconvolution: A Geometric Approach

Many signals arising in science and engineering can be modeled as sparse superpositions of localized, recurring motifs, occuring in different locations in the underlying space.
In such cases, we may want to recover the motif and their superposition locations from the raw signal. One approach for doing so is to express this *short and sparse deconvolution (SaSD)* task as an optimization problem.


{{< rawhtml >}}
<p style="text-align:center;">
<img src="/images/projects/sasd-stm.png" width="60%"/>
</p>
{{< /rawhtml >}}


Unfortunately, this optimization problem is nonconvex. We investigated its objective landscape and formalized its properties under a [*sparsity-coherence tradeoff*](https://arxiv.org/abs/1901.00256). When the tradeoff is satisfied, the landscape is benign and its properties allow us to design and apply manifold optimization algorithms for solving SaSD.

{{< rawhtml >}}
<p style="text-align:center;">
<img src="/images/projects/sasd-geometry.png" width="50%"/>
</p>
{{< /rawhtml >}}

We apply these techiniques in a range of practical scenarios ranging from [calcium fluoresence imaging](https://arxiv.org/abs/1908.10959) to [scanning tunneling electron microscopy](https://www.nature.com/articles/s41467-020-14633-1), and show that they are effective at resolving and extracting crucial information in these problem settings.

