<template>
  <div class="container">
    <h1>CSS Selector Showcase</h1>
    <div class="selector-grid">
      <div v-for="(selector, index) in selectors" :key="index" class="selector">
        <h3>{{ selector.name }}</h3>
        <div class="item-grid" :class="selector.class">
          <div v-for="n in 12" :key="n" class="item" :data-number="n">🐶</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectors: [
        { name: ':first-child', class: 'first-child' },
        { name: ':last-child', class: 'last-child' },
        { name: ':nth-child(even)', class: 'nth-child-even' },
        { name: ':nth-child(odd)', class: 'nth-child-odd' },
        { name: ':nth-child(2)', class: 'nth-child-2' },
        { name: ':nth-child(4n)', class: 'nth-child-4n' },
        { name: ':nth-child(n+3)', class: 'nth-child-n-plus-3' },
        { name: ':nth-child(-n+3)', class: 'nth-child-minus-n-plus-3' },
        { name: ':nth-child(3n+1)', class: 'nth-child-3n-plus-1' },
        { name: ':nth-child(3n-1)', class: 'nth-child-3n-minus-1' },
        { name: ':nth-last-child(3)', class: 'nth-last-child-3' },
      ],
    };
  },
};
</script>

<style lang="css">
.container {
  padding: 2rem;
  text-align: center;
  font-family: Arial, sans-serif;
  background-color: #f9f9f9;
}

h1 {
  color: #333;
  margin-bottom: 2rem;
}

.selector-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
}

.selector {
  width: 300px;
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 1rem;
}

.selector h3 {
  font-size: 1.1rem;
  color: #555;
  margin-bottom: 1rem;
}

.item-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

.item {
  font-size: 2rem;
  background-color: #eee;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative; 
  margin: auto; 
  transition: background-color 0.3s ease;
}

.item::after {
  content: attr(data-number);
  font-size: 0.8rem;
  color: #888;
  position: absolute;
  top: 10px;
  right: 10px;
  background: #ffffff;
  border-radius: 50%;
  padding: 2px 5px;
  font-weight: bold;
}

.first-child .item:first-child {
  background-color: #ff9aa2;
}

.last-child .item:last-child {
  background-color: #ffb7b2;
}

.nth-child-even .item:nth-child(even) {
  background-color: #ffdac1;
}

.nth-child-odd .item:nth-child(odd) {
  background-color: #e2f0cb;
}

.nth-child-2 .item:nth-child(2) {
  background-color: #a2e1db;
}

.nth-child-4n .item:nth-child(4n) {
  background-color: #b5ead7;
}

.nth-child-n-plus-3 .item:nth-child(n+3) {
  background-color: #c7ceea;
}

.nth-child-minus-n-plus-3 .item:nth-child(-n+3) {
  background-color: #ffc2e2;
}

.nth-child-3n-plus-1 .item:nth-child(3n+1) {
  background-color: #ff9aa2;
}

.nth-child-3n-minus-1 .item:nth-child(3n-1) {
  background-color: #ffb7b2;
}

.nth-last-child-3 .item:nth-last-child(3) {
  background-color: #ffdac1;
}

@media (max-width: 768px) {
  .item {
    width: 80px;
    height: 80px;
    font-size: 2.5rem;
  }

  .item-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
  }
}
</style>
