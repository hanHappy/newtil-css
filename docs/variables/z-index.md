<script setup>
import ExampleSection from "../components/ExampleSection.vue"
</script>

# z-index

변수 `var(--z-index)`는 z축에서의 우선순위를 정의하는 데 사용되며, 다음의 유틸리티에서 활용되고 있습니다:

-   [z-index](../utility/z-index.md)

## Default

다섯 단계의 순서값이 기본 제공됩니다.

<ExampleSection>
<div class="w:full d:flex jc:center of:auto">
    <div v-for="i in 5"
        class="c:base-1 border border-w:3 border-c:base-1 border-rd:4 bg-color:main-2 w:10 h:10 p:7 d:flex ai:center jc:center box"
        :class="`zi:${6-i}`">
        {{ 6-i }}
    </div>
</div>
</ExampleSection>

```html
<div class="zi:5 ...">5</div>
<div class="zi:4 ...">4</div>
<div class="zi:3 ...">3</div>
<div class="zi:2 ...">2</div>
<div class="zi:1 ...">1</div>
```

```css
:root {
    --z-index-1: 1;
    --z-index-2: 200;
    --z-index-3: 500;
    --z-index-4: 1000;
    --z-index-5: 2000;
}
```

## Overriding

다음과 같이 단계를 재정의하거나 추가할 수 있습니다.

<ExampleSection>
<div class="w:full d:flex jc:center of:auto">
    <div v-for="i in [1, 2, 3, 7, 6, 5, 4]"
        class="c:base-1 border border-w:3 border-c:base-1 border-rd:4 bg-color:main-2 w:10 h:10 p:7 d:flex ai:center jc:center box"
        :style="`z-index:${i}`">
        {{ i }}
    </div>
</div>
</ExampleSection>

```html
<div class="zi:1 ...">1</div>
<div class="zi:2 ...">2</div>
<div class="zi:3 ...">3</div>
<div class="zi:7 ...">7</div>
<div class="zi:6 ...">6</div>
<div class="zi:5 ...">5</div>
<div class="zi:4 ...">4</div>
```

```css
:root {
    --z-index-1: 1;
    --z-index-2: 200;
    --z-index-3: 500;
    --z-index-4: 1000; /* [!code --] */
    --z-index-5: 2000; /* [!code --] */
    --z-index-4: 800; /* [!code ++] */
    --z-index-5: 1000; /* [!code ++] */
    --z-index-6: 1200; /* [!code ++] */
    --z-index-7: 2000; /* [!code ++] */
}
```

<style scoped>
    .box {
        margin-right: -8px;
    }
    .box:not(:first-child) {
        margin-left: -8px;
    }
</style>
