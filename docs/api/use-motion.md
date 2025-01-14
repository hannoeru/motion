# useMotion

useMotion is the **core** composable of this **package**.

This composable **imports** every other **composable** and **expose** a **motion instance**.

[**useMotionProperties**](/api/use-motion-properties) is used to make the **element** styling properties **reactive**.

[**useMotionTransitions**](/api/use-motion-transitions) is used to manage **transitions** scheduling and **execution**.

[**useMotionVariants**](/api/use-motion-variants) is used to handle **variants** and variant **selection**.

[**useMotionControls**](/api/use-motion-controls) is used to create motion **controls** from variants, properties and transitions.

[**useMotionFeatures**](/api/use-motion-features) is used to register **lifecycle** hooks bindings, **visibility** and **events** listeners.

## Parameters

### `target`

Target must be an element (**SVG** / **HTML**), or a reference to an element.

If the target **reference** is **updated**, the **current** variant will be **applied** to the new **element**.

### `variants`

**Variants** must be an **object** or an object **reference**.

Keys are **variants** names, values are [**Variants Declarations**](/variants).

### `options`

Options is an **object**, supporting **4** parameters:

1. `syncVariants` (boolean): Whether or not the variants will be synchronized on update.
2. `lifeCycleHooks` (boolean): Whether or not the lifecycle hooks will be followed.
3. `visibilityHooks` (boolean): Whether or not the visibility hooks will be applied.
4. `eventListeners` (boolean): Whether or not the event listeners will be registered.

You should **not** be **pushed** to use those **options**, as if you are **not declaring** the related **variants**, they will **not** be **registered** anyway.

## Exposed

### `target`

Target is a **reference** to the **element** you passed as a **parameter**.

### `variant`

Variant is a **string** reference, from [**useMotionVariants**](/api/use-motion-variants).

### `variants`

Variants is a **reference** to the **variants** you passed as a **parameter**.

### `state`

State is a **computed reference** to the **current** variant **applied** to your **element**.

### `...controls`

Spread object from [**Motion Controls**](/api/use-motion-controls) exposed functions.

## Example

```typescript
const target = ref<HTMLElement>()

const variants = ref<MotionVariants>({
  initial: {
    opacity: 0,
  },
  enter: {
    opacity: 1,
  },
})

const motionInstance = useMotion(target, variants)
```
