<details open>
<summary>CSS Code Block</summary>

```css
/* -----------------------------------------------------------------------------
/* Comments
/* =============================================================================
/* I often use these!                                                         */

@import url("my-imported-styles.css");

:root {
    --an-example-colour-variable: #fff;
}

.gl-Card header {
  position: relative;
  display: flex;
  flex-wrap: wrap;
  text-align: center;
  justify-content: space-evenly;
  align-items: baseline;
  background: var(--color-card-lll);
  border: var(--spacing-px) solid var(--color-card-lll);
  border-bottom: transparent;
  border-top-left-radius: var(--border-radius);
  border-top-right-radius: var(--border-radius);

  .nightMode & {
    background: var(--color-nightmode-background-ddd);
    border: transparent;
  }
}

.gl-Card header h1 {
  flex: 0 0 100%;
  margin: 0 0 var(--spacing-one);
  padding: var(--spacing-half);
  border-bottom: var(--spacing-px) solid var(--color-card-ll);
  background: var(--color-card-llll);

  &:only-child {
    margin-bottom: 0;
  }

  &::before {
    content: '★ ';
  }

  .nightMode & {
    background: var(--color-nightmode-background-dddd);
  }
}

.gl-Card header h2 {
  margin: 0 0 var(--spacing-half);
  padding: var(--spacing-half);
  border-top-left-radius: var(--border-radius);
  border-top-right-radius: var(--border-radius);

  .nightMode & {
    color: var(--color-nightmode-text-light);
  }
}

.gl-Card header p {
  margin: 0 0 var(--spacing-half) 0;
  padding: var(--spacing-half);
}

.gl-Card_KeyPoint {
  /* pass */
}
```

</details>
