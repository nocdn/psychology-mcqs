<script>
  let { question, answers, correctAnswer } = $props();
  let selectedAnswer = $state("");
  let correctAnswerIndex = $state("");

  function checkAnswer() {
    if (answers[selectedAnswer] === correctAnswer) {
      correctAnswerIndex = selectedAnswer;
    }
  }
  let correctBackGroundColor = "#8CE78B";
  let incorrectBackGroundColor = "#FEE2E2";
</script>

<main class="h-fit bg-white border-2 rounded-lg p-5 flex flex-col gap-4 w-fit">
  <h1 class="font-semibold text-xl">{question}</h1>
  <ul class="flex flex-col gap-2">
    <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
    <li
      onmousedown={() => {
        selectedAnswer = "0";
        checkAnswer();
      }}
      style={selectedAnswer === "0"
        ? answers[0] === correctAnswer
          ? "background-color: #CCF6B8" // green for correct
          : "background-color: #FEE2E2" // red for incorrect
        : ""}
      class="border rounded-md px-4 py-3 cursor-pointer text-sm"
    >
      {answers[0]}
    </li>
    <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
    <li
      onmousedown={() => {
        selectedAnswer = "1";
        checkAnswer();
      }}
      style={selectedAnswer === "1"
        ? answers[1] === correctAnswer
          ? "background-color: #CCF6B8" // green for correct
          : "background-color: #FEE2E2" // red for incorrect
        : ""}
      class="border rounded-md px-4 py-3 cursor-pointer text-sm"
    >
      {answers[1]}
    </li>
    <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
    <li
      onmousedown={() => {
        selectedAnswer = "2";
        checkAnswer();
      }}
      style={selectedAnswer === "2"
        ? answers[2] === correctAnswer
          ? "background-color: #CCF6B8" // green for correct
          : "background-color: #FEE2E2" // red for incorrect
        : ""}
      class="border rounded-md px-4 py-3 cursor-pointer text-sm"
    >
      {answers[2]}
    </li>
    <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
    <li
      onmousedown={() => {
        selectedAnswer = "3";
        checkAnswer();
      }}
      style={selectedAnswer === "3"
        ? answers[3] === correctAnswer
          ? "background-color: #CCF6B8" // green for correct
          : "background-color: #FEE2E2" // red for incorrect
        : ""}
      class="border rounded-md px-4 py-3 cursor-pointer text-sm"
    >
      {answers[3]}
    </li>
  </ul>
</main>
