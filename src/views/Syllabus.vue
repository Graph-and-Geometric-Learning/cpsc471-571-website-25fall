<template>
  <v-container>
    <v-row>
      <v-col>
        <v-table>
          <thead>
            <tr>
              <th>Week</th>
              <th>Date</th>
              <th>Lecture</th>
              <th>Slides</th>
              <th>Readings</th>
              <th></th>
              <th>Deadlines</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in items" :key="item.date">
              <td><b>{{ item.week }}</b></td>
              <td>{{ item.date }}</td>
              <td>
                <p v-if="item.lecture == 'No class'" style="color:grey;">{{ item.lecture }}</p>
                <p v-else v-html="item.lecture"></p>
                <p v-if="item.event" style="color: green; font-size:11pt;">{{ item.event }}</p>
              </td>
              <td><a v-if="item.slide" :href="item.slide">[slide]</a><a v-if="item.record" :href="item.record">[record]</a></td>
              <td v-html="item.reading"></td>
              <td>
                <div v-if="item.new_api">
                  <div v-if="item.hw">
                    <a :href="item.hw">[{{ baseName(item.hw) }}]</a> released
                  </div>
                  <br v-if="item.colab" />
                  <div v-if="item.colab">
                    <a :href="item.colab">[{{ baseName(item.colab) }}]</a>
                    released
                  </div>
                </div>

              </td>
              <td><p style="color:red;">{{ item.deadline }}</p></td>
            </tr>
          </tbody>
        </v-table>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { defineComponent } from "vue";

interface Item {
  week: number;
  date: string;
  lecture: string;
  slide?: string;
  record?: string;
  reading?: string;
  event?: string;
  deadline?: string;
  hw?: string;
  colab?: string;
  new_api?: boolean;
}

var items: Item[] = [
  {
    week: 1,
    date: "Thu, Aug 28",
    lecture: "Introduction to Trustworthy AI",
    slide: import.meta.env.BASE_URL + "01-intro.pdf",
    reading: '<a href="https://arxiv.org/pdf/2205.03824" target="_blank">AI Sustainability</a>'
  },
  {
    week: 2,
    date: "Tue, Sep 2",
    lecture: "Deep Learning Basics, CNNs, and RNNs",
    slide: import.meta.env.BASE_URL + "02-basics.pdf",
    reading: '<a href="http://www.trustworthymachinelearning.com/" target="_blank">Trustworthy Machine Learning Book Chapter 1.1 Defining Trust</a>'
  },
  {
    week: 2,
    date: "Thu, Sep 4",
    lecture: "Transformers and Large Language Models (LLMs)",
    slide: import.meta.env.BASE_URL + "03-transformers.pdf",
    reading: '<a href="https://arxiv.org/abs/2401.05561" target="_blank">[2401.05561] TrustLLM: Trustworthiness in Large Language Models</a>',
    hw: import.meta.env.BASE_URL + "HW1_updated.pdf",
    new_api: true,
  },
  {
    week: 3,
    date: "Tue, Sep 9",
    lecture: "Explainability of Neural Networks (XAI)",
    slide: import.meta.env.BASE_URL + "04-explainability.pdf",
    reading: '<a href="https://arxiv.org/abs/1703.01365" target="_blank">Integrated Gradients</a>',
  },
  {
    week: 3,
    date: "Thu, Sep 11",
    lecture: "Local Explainability",
    slide: import.meta.env.BASE_URL + "05-surrogates.pdf",
    reading: `
    <a href="https://homes.cs.washington.edu/~marcotcr/blog/lime/" target="_blank">LIME</a><br/>
    <a href="https://arxiv.org/abs/1705.07874" target="_blank">SHAP</a>
    `
  },
  {
    week: 4,
    date: "Tue, Sep 16",
    lecture: "Explainability Evaluation",
    hw: import.meta.env.BASE_URL + "Programming Homework 1.zip",
    new_api: true,
    slide: import.meta.env.BASE_URL + "06-explainability_eval.pdf",
    reading: `
    <a href="https://arxiv.org/pdf/1710.10547.pdf" target="_blank">Explanations can also be vulnerable to adversarial attacks</a><br/>
    <a href="https://arxiv.org/pdf/2005.00631.pdf" target="_blank">Evaluating Explanations</a>
    `
  },
  {
    week: 4,
    date: "Thu, Sep 18",
    lecture: "Global Explainability",
  },
  {
    week: 5,
    date: "Tue, Sep 23",
    lecture: "LLM Interpretability",
    deadline: "[Due] Written Homework 1",
    slide: import.meta.env.BASE_URL + "07_mechanistic_Interpretability_for_LLMs.pdf",
  },
  {
    week: 5,
    date: "Thu, Sep 25",
    lecture: "Introduction to Adversarial Attacks",
    hw: import.meta.env.BASE_URL + "HW2.pdf",
    new_api: true,
    slide: import.meta.env.BASE_URL + "08_adversarial_evasion.pdf",
    reading: `
    <a href="https://arxiv.org/pdf/1712.07107.pdf" target="_blank">Adversarial Examples: Attacks and Defenses for Deep Learning</a><br/>
    <a href="https://arxiv.org/pdf/2111.09961.pdf" target="_blank">Review of Adversarial Attacks and Defense</a>
    `
  },
  {
    week: 6,
    date: "Tue, Sep 30",
    lecture: "Evasion Attacks and Defenses",
    deadline: "[Due] Coding Homework 1",
  },
  {
    week: 6,
    date: "Thu, Oct 2",
    lecture: "In-class work session",
    hw: import.meta.env.BASE_URL + "Programming Homework 2.zip",
    new_api: true,
    slide: import.meta.env.BASE_URL + "In-class work session.pdf",
    reading: `<a href="${import.meta.env.BASE_URL + 'CPSC 4710-5710 GPU access.pdf'}" target="_blank">CPSC 4710-5710 GPU access</a><br/>`
  },
  {
    week: 7,
    date: "Tue, Oct 7",
    lecture: "Poisoning Attacks and Defenses",
    slide: import.meta.env.BASE_URL + "09_defense_poison.pdf",
    reading: `<a href="https://dl.acm.org/doi/10.1145/3551636" target="_blank">A Comprehensive Survey on Poisoning Attacks and Countermeasures in Machine Learning</a>`
  },
  {
    week: 7,
    date: "Thu, Oct 9",
    lecture: "Exploratory Attacks and Defenses",
  },
  {
    week: 7,
    date: "Fri, Oct 10",
    lecture: "No class",
    deadline: "[Due] Written Homework 2",
  },
  {
    week: 8,
    date: "Tue, Oct 14",
    lecture: "Verification and Robust Reinforecement Learning: Zoom Lecture (<a href=\"https://yale.zoom.us/j/99111032117?from=addon\" target=\"_blank\">link</a>)",
    slide: import.meta.env.BASE_URL + "10_verification.pdf",
    reading: `<a href="https://arxiv.org/abs/2206.12227" target="_blank">Adversarial Robustness of Deep Neural Networks: A Survey from a Formal Verification Perspective</a>`
  },
  {
    week: 9,
    date: "Mon, Oct 20",
    lecture: "No class",
    hw: import.meta.env.BASE_URL + "HW3.pdf",
    new_api: true,
  }, 
  {
    week: 9,
    date: "Tue, Oct 21",
    lecture: "LLM Robustness",
    deadline: "[Due] Project proposal",
    slide: import.meta.env.BASE_URL + "11_llm_robustness.pdf",
    reading: `<a href="https://arxiv.org/pdf/2307.15043" target="_blank">Universal and Transferable Adversarial Attacks on Aligned Language Models</a><br/>
    <a href="https://arxiv.org/pdf/2402.09283" target="_blank">Attacks, Defenses and Evaluations for LLM Conversation Safety: A Survey</a><br/>
    <a href="https://www.arxiv.org/pdf/2510.06265" target="_blank">Large Language Models Hallucination: A Comprehensive Survey</a><br/>
    <a href="https://arxiv.org/pdf/2312.10997" target="_blank">Retrieval-Augmented Generation for Large Language Models: A Survey</a>`
  },
  {
    week: 9,
    date: "Thu, Oct 23",
    lecture: "Differential Privacy",
    deadline: "[Due] Coding Homework 2",
    slide: import.meta.env.BASE_URL + "12-privacy.pdf",
  },
  {
    week: 10,
    date: "Tue, Oct 28",
    lecture: "Machine Unlearning",
    slide: import.meta.env.BASE_URL + "13-unlearning.pdf",
  },
  {
    week: 10,
    date: "Thu, Oct 30",
    lecture: "Federated Learning",
    slide: import.meta.env.BASE_URL + "14-federated_learning.pdf",
  },
  {
    week: 10,
    date: "Mon, Nov 3",
    lecture: "No class",
    deadline: "[Due] Written Homework 3",
  },
  {
    week: 11,
    date: "Tue, Nov 4",
    lecture: "LLM Privacy",
  },
  {
    week: 11,
    date: "Thu, Nov 6",
    lecture: "Algorithmic Fairness in ML",
    slide: import.meta.env.BASE_URL + "15-fairness.pdf",
  },
  {
    week: 12,
    date: "Tue, Nov 11",
    lecture: "Fairness in LLMs",
  },
  {
    week: 12,
    date: "Thu, Nov 13",
    lecture: "Quantization",
  },
  {
    week: 12,
    date: "Fri, Nov 14",
    lecture: "No class",
    deadline: "[Due] Project Milestone",
  },
  {
    week: 13,
    date: "Tue, Nov 18",
    lecture: "Guest Lecture by Prof. Arman Cohan on Security and Privacy of LLMs (In-person)",
  },
  {
    week: 13,
    date: "Thu, Nov 20",
    lecture: "Revise and Prepare for Exam",
  },
  {
    week: 15,
    date: "Tue, Dec 2",
    lecture: "Guest Lecture",
  },
  {
    week: 15,
    date: "Thu, Dec 4",
    lecture: "Exam",
  },
  {
    week: 16,
    date: "Thu, Dec 11",
    lecture: "No class",
    deadline: "[Due] Final project report (strict deadline)",
  },
];

export default defineComponent({
  name: "Syllabus",

  data: () => ({
    items: items,
  }),
  methods: {
    baseName(str) {
      var base = new String(str).substring(str.lastIndexOf("/") + 1);
      if (base.lastIndexOf(".") != -1)
        base = base.substring(0, base.lastIndexOf("."));
      return base;
    },
  },
});
</script>
