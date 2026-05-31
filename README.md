

- **Card-based layout** for superheroes
- **Universe-based theming** (Marvel = Red/Blue, DC = Blue/Yellow)
- **Hover effects** and responsive design

Save this as `styles.css` in your project:

```css
/* Base Styles */
:root {
  --marvel-primary: #e62429;
  --marvel-secondary: #1560bd;
  --dc-primary: #006dc4;
  --dc-secondary: #ffd100;
  --text-light: #f8f9fa;
  --text-dark: #212529;
  --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  --transition: all 0.3s ease;
}

body {
  font-family: 'Segoe UI', 'Oxygen', 'Ubuntu', sans-serif;
  background-color: #f5f5f5;
  color: var(--text-dark);
  line-height: 1.6;
  padding: 20px;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 20px;
}

h1 {
  text-align: center;
  margin-bottom: 30px;
  color: var(--text-dark);
  font-size: 2.5rem;
}

/* Universe Toggle */
.universe-toggle {
  display: flex;
  justify-content: center;
  margin-bottom: 30px;
  gap: 10px;
}

.universe-toggle button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
  transition: var(--transition);
}

.universe-toggle button.active {
  box-shadow: var(--shadow);
}

.universe-toggle button.marvel {
  background-color: var(--marvel-primary);
  color: var(--text-light);
}

.universe-toggle button.dc {
  background-color: var(--dc-primary);
  color: var(--text-light);
}

/* Superhero Grid */
.superhero-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 25px;
  margin-bottom: 40px;
}

.superhero-card {
  background-color: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: var(--shadow);
  transition: var(--transition);
  position: relative;
}

.superhero-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
}

.superhero-card.marvel::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 8px;
  background: linear-gradient(90deg, var(--marvel-primary), var(--marvel-secondary));
}

.superhero-card.dc::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 8px;
  background: linear-gradient(90deg, var(--dc-primary), var(--dc-secondary));
}

.superhero-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.superhero-info {
  padding: 20px;
}

.superhero-name {
  font-size: 1.5rem;
  margin-bottom: 10px;
  color: var(--text-dark);
}

.superhero-universe {
  display: inline-block;
  padding: 3px 8px;
  border-radius: 4px;
  font-size: 0.8rem;
  font-weight: bold;
  margin-bottom: 10px;
  color: white;
}

.superhero-universe.marvel {
  background-color: var(--marvel-primary);
}

.superhero-universe.dc {
  background-color: var(--dc-primary);
}

.superhero-description {
  margin-bottom: 15px;
  font-size: 0.95rem;
  color: #495057;
}

.superhero-powers {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 15px;
}

.superhero-power {
  background-color: #e9ecef;
  padding: 4px 8px;
  border-radius: 20px;
  font-size: 0.8rem;
}

/* Search and Filters */
.search-filter {
  display: flex;
  justify-content: space-between;
  margin-bottom: 30px;
  gap: 20px;
}

.search-box {
  flex: 1;
  padding: 12px;
  border: 1px solid #ced4da;
  border-radius: 5px;
  font-size: 1rem;
}

.filter-select {
  padding: 12px;
  border: 1px solid #ced4da;
  border-radius: 5px;
  font-size: 1rem;
  background-color: white;
}

/* Responsive Design */
@media (max-width: 768px) {
  .superhero-grid {
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  }

  .search-filter {
    flex-direction: column;
  }
}

@media (max-width: 480px) {
  .superhero-grid {
    grid-template-columns: 1fr;
  }
}
```

### Key Features:
1. **Universe Theming**:
   - Marvel cards have a red/blue gradient header.
   - DC cards have a blue/yellow gradient header.

2. **Responsive Grid**:
   - Adjusts from 4 columns (desktop) to 1 column (mobile).

3. **Interactive Elements**:
   - Hover effects on cards.
   - Universe toggle buttons.

4. **Search/Filter**:
   - Ready-to-use search box and filter dropdown.

5. **Power Tags**:
   - Styled tags for superhero abilities.

### How to Use:
1. Link this CSS file in your HTML:
   ```html
   <link rel="stylesheet" href="styles.css">
   ```

2. Structure your HTML like this:
   ```html
   <div class="superhero-grid">
     <div class="superhero-card marvel">
       <img src="ironman.jpg" alt="Iron Man" class="superhero-image">
       <div class="superhero-info">
         <h3 class="superhero-name">Iron Man</h3>
         <span class="superhero-universe marvel">Marvel</span>
         <p class="superhero-description">Genius billionaire playboy philanthropist...</p>
         <div class="superhero-powers">
           <span class="superhero-power">Genius Intellect</span>
           <span class="superhero-power">Powered Armor</span>
         </div>
       </div>
     </div>
     <!-- More superhero cards... -->
   </div>
   ```
