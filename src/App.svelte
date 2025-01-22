<script>
  import { ArrowRight } from "lucide-svelte";
  import { ArrowLeft } from "lucide-svelte";
  import Card from "./lib/Card.svelte";

  const questionsAndAnswers = [
    {
      question:
        "According to the lecture notes, what is a key limitation of defining mental health issues solely through 'statistical infrequency'?",
      options: [
        "It assumes that mental health disorders are increasing dramatically, when statistics have shown this is not the case",
        "It assumes mental health disorders are rare, despite 1 in 8 people having a mental health disorder.",
        "It focuses on distress rather than violations of social norms, when this has been shown to be incorrect.",
        "It assumes behaviours are always abnormal and doesn't take into consideration context, or how common it may be in reality.",
      ],
      answer:
        "It assumes mental health disorders are rare, despite 1 in 8 people having a mental health disorder.",
    },
    {
      question:
        "According to the lecture notes, what is a key feature of the International Classification of Diseases (ICD) compared to the DSM?",
      options: [
        "The ICD is more valued for research purposes as the information is more robust",
        "The ICD provides more specific, quantitative descriptions of disorders.",
        "The ICD is freely available and tends to be simpler and more qualitative than the DSM",
        "The ICD includes all of the disorders listed in the DSM, as well as many more.",
      ],
      answer:
        "The ICD is freely available and tends to be simpler and more qualitative than the DSM",
    },
    {
      question:
        "According to the notes, what was the primary issue leading to the fall in credibility of DID (Dissociative Identity Disorder) in popular culture?",
      options: [
        "The lack of a medical definition of DID in the DSM",
        "Exposure of the 'Sybil' case, showing that the individual had been coached to create multiple personalities.",
        "The inability to differentiate between DID and PTSD.",
        "The lack of positive outcomes following treatments of DID.",
      ],
      answer:
        "Exposure of the 'Sybil' case, showing that the individual had been coached to create multiple personalities.",
    },
  ];

  let currentQuestionIndex = $state(0);
</script>

<main class="w-screen h-screen grid place-items-center px-32">
  <Card
    question={questionsAndAnswers[currentQuestionIndex].question}
    answers={questionsAndAnswers[currentQuestionIndex].options}
    correctAnswer={questionsAndAnswers[currentQuestionIndex].answer}
  />
  <div class="flex gap-3">
    <button
      onclick={() => {
        currentQuestionIndex = currentQuestionIndex - 1;
      }}
      class="text-sm font-bold font-mono flex gap-4 items-center border border-input dark:border-gray-500 rounded-md px-4 py-2 hover:bg-[#EEF2FF] hover:text-blue-800 hover:outline-1 hover:outline-dashed hover:outline-[#3d3f85]"
    >
      <ArrowLeft size={16} />
      Back
    </button>
    <button
      onclick={() => {
        currentQuestionIndex = currentQuestionIndex + 1;
      }}
      class="text-sm font-bold font-mono flex gap-4 items-center border border-input dark:border-gray-500 rounded-md px-4 py-2 hover:bg-[#EEF2FF] hover:text-blue-800 hover:outline-1 hover:outline-dashed hover:outline-[#3d3f85]"
    >
      Next
      <ArrowRight size={16} />
    </button>
  </div>
</main>
