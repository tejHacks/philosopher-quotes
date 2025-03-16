<template>
  <div class="quotes-app">
    <h1 class="title">Philosophical Quotes</h1>
    <div class="quote-box">
      <p class="quote">"{{ currentQuote.text }}"</p>
      <p class="author">- {{ currentQuote.author }}</p>
      <button @click="getRandomQuote" class="new-quote-button">New Quote</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quotes: [
        { text: "An unexamined life is not worth living.", author: "Socrates" },
        { text: "You have power over your mind – not outside events. Realize this, and you will find strength.", author: "Marcus Aurelius" },
        { text: "Impossible is a word to be found only in the dictionary of fools.", author: "Napoleon Bonaparte" },
        { text: "Happiness depends upon ourselves.", author: "Aristotle" },
        { text: "The only true wisdom is in knowing you know nothing.", author: "Socrates" },
        { text: "Dwell on the beauty of life. Watch the stars, and see yourself running with them.", author: "Marcus Aurelius" },
        { text: "The greatest wealth is to live content with little.", author: "Plato" },
  { text: "The aim of art is to represent not the outward appearance of things, but their inward significance.", author: "Aristotle" },
  { text: "To know that you do not know is the best. To think you know when you do not is a disease. Recognizing this disease as a disease is to be free of it.", author: "Lao Tzu" },
  { text: "The impediment to action advances action. What stands in the way becomes the way.", author: "Marcus Aurelius" },
  { text: "Man is condemned to be free; because once thrown into the world, he is responsible for everything he does.", author: "Jean-Paul Sartre" },
  { text: "What worries you masters you.", author: "Haddon Robinson" },
  { text: "Where there is much desire to learn, there of necessity will be much argument, much writing with the pen, and many opinions; for opinion in good men is but knowledge in the making.", author: "John Milton" },
  { text: "The privilege of absurdity; to which no living creature is subject, but man only.", author: "Thomas Hobbes" },
  { text: "The mind is everything. What you think you become.", author: "Buddha" },
  { text: "Change your thoughts and you change your world.", author: "Norman Vincent Peale" },
  { text: "The best index to a person's character is how he treats people who can't do him any good, and how he treats people who can't fight back.", author: "Abigail Van Buren" },
  { text: "The unexamined life is not worth living.", author: "Socrates" },
  { text: "The only way to deal with an unfree world is to become so absolutely free that your very existence is an act of rebellion.", author: "Albert Camus" },
  { text: "The most certain sign of wisdom is continued cheerfulness.", author: "Michel de Montaigne" },
  { text: "To be yourself in a world that is constantly trying to make you something else is the greatest accomplishment.", author: "Ralph Waldo Emerson" },
  { text: "There is only one good, knowledge, and one evil, ignorance.", author: "Socrates" },
  { text: "It is not death that a man should fear, but he should fear never beginning to live.", author: "Marcus Aurelius" },
  { text: "Those who cannot remember the past are condemned to repeat it.", author: "George Santayana" },
  { text: "The true sign of intelligence is not knowledge but imagination.", author: "Albert Einstein" },
  { text: "The happiness of your life depends upon the quality of your thoughts.", author: "Marcus Aurelius" },
  { text: "The world as we have created it is a process of our thinking. It cannot be changed without changing our thinking.", author: "Albert Einstein" },
  { text: "Knowing yourself is the beginning of all wisdom.", author: "Aristotle" },
  { text: "The journey of a thousand miles begins with a single step.", author: "Lao Tzu" },
  { text: "What lies behind us and what lies before us are tiny matters compared to what lies within us.", author: "Ralph Waldo Emerson" },
  { text: "The greatest glory in living lies not in never falling, but in rising every time we fall.", author: "Nelson Mandela" },
  { text: "The function of prayer is not to influence God, but rather to change the nature of the one who prays.", author: "Søren Kierkegaard" },
  { text: "The best way to predict the future is to create it.", author: "Peter Drucker" },
  { text: "The purpose of life is not to be happy. It is to be useful, to be honorable, to be compassionate, to have it make some difference that you have lived and lived well.", author: "Ralph Waldo Emerson" },
  { text: "The only limit to our realization of tomorrow will be our doubts of today.", author: "Franklin D. Roosevelt" },
  { text: "The truth is rarely pure and never simple.", author: "Oscar Wilde" },
  { text: "To live is to suffer, to survive is to find some meaning in the suffering.", author: "Friedrich Nietzsche" },
  { text: "The aim of the wise is not to secure pleasure, but to avoid pain.", author: "Aristotle" },
  { text: "The superior man is distressed by his want of ability. The inferior man is distressed by his want of money.", author: "Confucius" },
  { text: "The art of progress is to preserve order amid change and to preserve change amid order.", author: "Alfred North Whitehead" },
  { text: "The most valuable of all talents is that of never using two words when one will do.", author: "Thomas Jefferson" },
  { text: "To see what is right and not to do it is a lack of courage.", author: "Confucius" },
  { text: "The price of freedom is eternal vigilance.", author: "Thomas Jefferson" },
  { text: "The secret of getting ahead is getting started.", author: "Mark Twain" },
  { text: "The true measure of a man is how he treats someone who can do him absolutely no good.", author: "Samuel Johnson" },
  { text: "The only thing necessary for the triumph of evil is for good men to do nothing.", author: "Edmund Burke" },
  { text: "The best revenge is massive success.", author: "Frank Sinatra" },
  { text: "The future belongs to those who believe in the beauty of their dreams.", author: "Eleanor Roosevelt" },
  { text: "The greatest weapon against stress is our ability to choose one thought over another.", author: "William James" },
  { text: "The only source of knowledge is experience.", author: "Albert Einstein" },
  { text: "The difference between genius and stupidity is that genius has its limits.", author: "Albert Einstein" },
  { text: "The best and most beautiful things in the world cannot be seen or even touched - they must be felt with the heart.", author: "Helen Keller" },
  { text: "The greatest mistake you can make in life is to be continually fearing you will make one.", author: "Elbert Hubbard" },
  { text: "The ultimate value of life depends upon awareness and the power of contemplation rather than upon mere survival.", author: "Aristotle" },
  { text: "The true sign of a man's superiority is his questionning.", author: "Albert Einstein" },
  { text: "The most wasted of all days is one without laughter.", author: "E.E. Cummings" },
  { text: "Doubt is the origin of wisdom.", author: "Simone Weil" },
  { text: "The beginning of thought is in disagreement—not only with others but also with ourselves.", author: "Eric Hoffer" },
  { text: "Wisdom begins in wonder.", author: "Socrates" },
  { text: "To be conscious that you are ignorant is a great step to knowledge.", author: "Benjamin Disraeli" },
  { text: "The aim of the wise is not to secure pleasure, but to avoid pain.", author: "Aristotle" },
  { text: "The only way to do great work is to love what you do.", author: "Steve Jobs" },
  { text: "The purpose of learning is growth, and our minds, unlike our bodies, can continue growing as we continue to live.", author: "Mortimer J. Adler" },
  { text: "What we learn with pleasure we never forget.", author: "Alfred Mercier" }
      ],
      currentQuote: {}
    };
  },
  methods: {
    getRandomQuote() {
      const randomIndex = Math.floor(Math.random() * this.quotes.length);
      this.currentQuote = this.quotes[randomIndex];
    }
  },
  created() {
    this.getRandomQuote();
  }
};
</script>

<style scoped>
.quotes-app {
  text-align: center;
  max-width: 600px;
  margin: auto;
  background: #2e2b22;
  color: #f5e6c8;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.3);
  font-family: 'Merriweather', serif;
  border: 2px solid #c2a97a;
}
.title {
  font-size: 28px;
  margin-bottom: 20px;
  font-family: 'Cormorant Garamond', serif;
  font-weight: bold;
  letter-spacing: 1px;
  color: #e0c097;
}
.quote-box {
  font-size: 20px;
  font-style: italic;
  padding: 25px;
  background: rgba(50, 47, 37, 0.9);
  border-radius: 10px;
  box-shadow: 2px 2px 15px rgba(0, 0, 0, 0.2);
  border: 1px solid #b59e77;
  position: relative;
}
.quote-box::before {
  content: "\201C";
  font-size: 40px;
  position: absolute;
  left: 10px;
  top: 5px;
  color: #c2a97a;
}
.quote-box::after {
  content: "\201D";
  font-size: 40px;
  position: absolute;
  right: 10px;
  bottom: 5px;
  color: #c2a97a;
}
.author {
  font-size: 18px;
  margin-top: 15px;
  font-weight: bold;
  color: #e0c097;
}
.new-quote-button {
  background: #8b6f47;
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 16px;
  font-weight: bold;
  border-radius: 8px;
  cursor: pointer;
  margin-top: 20px;
  transition: background 0.3s;
}
.new-quote-button:hover {
  background: #a07e5c;
}
</style>
