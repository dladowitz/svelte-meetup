<script>
  import Header from "./UI/Header.svelte";
  import MeetupItem from "./Meetups/MeetupItem.svelte";

  const meetups = [
    {
      id: 'm1',
      title: 'Svelte Talks ',
      subtitle: 'Learn to code in 2 hours',
      description: "We'll learn to code and lots of other things",
      imageUrl: 'https://dynaimage.cdn.cnn.com/cnn/c_fill,g_auto,w_1200,h_675,ar_16:9/https%3A%2F%2Fcdn.cnn.com%2Fcnnnext%2Fdam%2Fassets%2F190410085534-5g-cities-restricted.jpg',
      address: '50 Beale st, SF, CA', 
      contactEmail: 'someone@someplace.com'
    },
    {
      id: 'm2',
      title: 'Rock Climbing',
      subtitle: 'Climbing and things',
      description: "We'll learn to climb and lots of other things",
      imageUrl: 'https://images.unsplash.com/photo-1480714378408-67cf0d13bc1b?ixlib=rb-1.2.1&w=1000&q=80',
      address: '50 Beale st, SF, CA', 
      contactEmail: 'someone@someplace.com'
    }
  ];

</script>

<style>
  .meetups {
    margin-top: 6rem;
  }
</style>

<Header />

<section class="meetups">
  <div>
  {#each meetups as meetup, index (meetup.id)}
    <MeetupItem
      title = {meetup.title}
      subtitle = {meetup.subtitle}
      description = {meetup.description}
      imageUrl = {meetup.imageUrl}
      address = {meetup.address}
      contactEmail = {meetup.contactEmail}
    />
  {/each}
</div>
  
</section>


