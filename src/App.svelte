<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import TextInput from "./UI/TextInput.svelte";
  import Button from "./UI/Button.svelte";

  let title = "";
  let subtitle = ""; 
  let description = "";
  let imageUrl = "";
  let address = "";
  let contactEmail = "";

  let meetups = [
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

  function addMeetup(){

    meetups = [{
      id: Math.random().toString(),  
      title,
      subtitle,
      description,
      imageUrl,
      address,
      contactEmail
    }, ...meetups]
  }

</script>

<style>
  main {
    margin-top: 4em;
  }

  form {
    width: 30rem;
    max-width: 90%;
    margin: auto;
  }
</style>

<Header />

<main>
  <form on:submit|preventDefault="{addMeetup}">
    <TextInput 
      id="title"
      label="Title"
      value={title}
      on:input={(event) => (title = event.target.value)}
    />

    <TextInput 
      id="subtitle"
      label="Subtitle"
      value={subtitle}
      on:input={(event) => (subtitle = event.target.value)}
    />

    <TextInput 
      controlType="textarea"
      id="description"
      label="Description"
      rows=3
      value={description}
      on:input={(event) => (description = event.target.value)}
    />

    <TextInput 
      id="imageUrl"
      label="Image Url"
      value={imageUrl}
      on:input={(event) => (imageUrl = event.target.value)}
    />

    <TextInput 
      id="address"
      label="Address"
      value={address}
      on:input={(event) => (address = event.target.value)}
    /> 

    <TextInput 
      id="contactEmail"
      label="Contact Email"
      value={contactEmail}
      on:input={(event) => (contactEmail = event.target.value)}
      type="email"
    />

    <Button type="submit" caption="Save" />
  </form>


  <MeetupGrid {meetups}/>
</main>




