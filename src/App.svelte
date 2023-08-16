<script>
  import FeedbackForm from "./lib/FeedbackForm.svelte";
  import FeedbackList from "./lib/FeedbackList.svelte";
  import FeedbackStats from "./lib/FeedbackStats.svelte";


  let feedback = [
    {
      id: 1,
      rating: 10,
      text: "orem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scra"
    },
    {
      id: 2,
      rating: 4,
      text: "orem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scra"
    },
    {
      id: 3,
      rating: 7,
      text: "orem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scra"
    },
    {
      id: 4,
      rating: 2,
      text: "orem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scra"
    }
  ];

  $: count =  feedback.length
  $: average = feedback.reduce((a, {rating})=> a+rating, 0) / feedback.length

const deleteFeedback = (e) =>{
  const itemId = e.detail;
  feedback = feedback.filter((item) => item.id != itemId);
}
</script>

<main class="container">
  <FeedbackForm />
  <FeedbackStats {count} {average}/>
  <FeedbackList {feedback} on:delete-feedback = {deleteFeedback} />
</main>

