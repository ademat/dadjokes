<template>
  <div class="app">
    <Joke
      v-for="(joke,index) in jokes"
      :jokeText="joke.jokeText"
      :upLikes="joke.upLikes"
      :downLikes="joke.downLikes"
      :user="joke.user"
      :idx="index"
      @giveUpLike="giveUpLike"
      @giveDownLike="giveDownLike"
      :key="index"
    />
  </div>
</template>

<script>
import Joke from "./Joke.vue";
export default {
  name: "App",
  components: {
    Joke: Joke
  },
  methods: {
    giveUpLike(idx) {
      this.jokes[idx].upLikes++;
    },
    giveDownLike(idx) {
      this.jokes[idx].downLikes++;
    }
  },
  data() {
    return {
      jokes: [
        {
          jokeText: `The secret service isn't allowed to yell "Get down!" anymore when the president is about to be attacked. Now they have to yell "Donald, duck!"`,
          upLikes: 13,
          downLikes: 24,
          user: "user01"
        },
        {
          jokeText: `Why did the invisible man turn down the job offer? He couldn't see himself doing it.`,
          upLikes: 50,
          downLikes: 10,
          user: "user02"
        },
        {
          jokeText: `I bought some shoes from a drug dealer. I don't know what he laced them with, but I was tripping all day!`,
          upLikes: 30,
          downLikes: 2,
          user: "user03"
        },
        {
          jokeText: `Did you hear the news? FedEx and UPS are merging. They’re going to go by the name Fed-Up from now on.`,
          upLikes: 15,
          downLikes: 8,
          user: "user04"
        },
        {
          jokeText: `My daughter screeched, "Daaaaaad, you haven't listened to one word I've said, have you!?" What a strange way to start a conversation with me...`,
          upLikes: 90,
          downLikes: 44,
          user: "user05"
        },
        {
          jokeText: `My wife tried to unlatch our daughter's car seat with one hand and said, "How do one armed mothers do it?" Without missing a beat I replied, "Single handedly."`,
          upLikes: 38,
          downLikes: 1,
          user: "user06"
        },
        {
          jokeText: `When a dad drives past a graveyard: Did you know that's a popular cemetery? Yep, people are just dying to get in there!`,
          upLikes: 66,
          downLikes: 35,
          user: "user07"
        },
        {
          jokeText: `My friend keeps saying "cheer up man it could be worse, you could be stuck underground in a hole full of water." I know he means well.`,
          upLikes: 27,
          downLikes: 18,
          user: "user08"
        },
        {
          jokeText: `The fattest knight at King Arthur’s round table was Sir Cumference. He acquired his size from too much pi`,
          upLikes: 42,
          downLikes: 9,
          user: "user09"
        }
      ]
    };
  }
};
</script>

<style scoped>
</style>