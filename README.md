# CSS Zero

An opinionated CSS starter kit for your application. You can think of it like a "no build" Tailwind CSS.

## Installation

```
bundle add css-zero
```

This gem requires [Propshaft](https://github.com/rails/propshaft), make sure to load all the CSS files in your layout.html.erb.

```html+erb
<%= stylesheet_link_tag :all, "data-turbo-track": "reload" %>
```

## Usage

```html
<h1 class="text-xl font-bold mb-4">
  Write most page content using utility classes.
</h1>

<div class="component">
  Write custom CSS using predefined variables for components.
</div>
```

```css
.component {
  background-color: var(--red-500);
  border-radius: var(--rounded);
  block-size: var(--size-4);
}
```

Check the [CSS files](app/assets/stylesheets) in the repository for reference.

## Example

<img width="600" alt="Example" src="https://github.com/lazaronixon/css-zero/assets/2651240/3042ec7e-c30e-4047-9b85-2abc357683fd">

<details>
<summary>Code</summary>

```html+erb
<div class="flex flex-col mb-10 items-center" style="gap: 4rem">
  <form method="post" class="flex flex-col w-full gap" style="max-inline-size: 24rem;">
    <div class="flex flex-col grow gap-small">
      <label for="name_field" class="text-sm font-medium">Full name</label>
      <input type="text" id="name_field" class="input" minlength="2" required>
    </div>

    <div class="flex flex-col gap-small">
      <label for="date_field" class="text-sm font-medium">Date picker</label>
      <input type="date" id="date_field" class="input">
    </div>

    <div class="flex flex-col gap-small">
      <label for="file_field" class="text-sm font-medium">File</label>
      <input type="file" id="file_field" class="input">
    </div>

    <div class="flex flex-col gap-small">
      <label for="age_range_field" class="text-sm font-medium">Age Range</label>
      <select id="age_range_field" class="input">
        <option value="0-13">0-13</option>
        <option value="14-17">14-17</option>
      </select>
    </div>

    <div class="flex flex-col gap-small">
      <label for="comment_field" class="text-sm font-medium">Comment</label>
      <textarea id="comment_field" rows="3" class="input"></textarea>
    </div>

    <label class="flex items-center gap-small" for="terms">
      <input type="checkbox" class="switch" id="terms">
      <span class="text-sm font-medium">Accept terms and conditions</span>
    </label>
  </form>

  <div class="flex justify-center gap">
    <button class="btn">Primary</button>
    <button class="btn btn--secondary">Secondary</button>
    <button class="btn btn--outline">Outline</button>
    <button class="btn btn--plain">Plain</button>
    <button class="btn btn--positive">Positive</button>
    <button class="btn btn--negative">Negative</button>

    <button class="btn">
      <%= image_tag "plus.svg", role: "presentation", size: 20 %>
      <span>With icon</span>
    </button>
  </div>

  <table class="table" style="max-inline-size: 45rem;">
    <thead>
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Access</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="font-medium">Leslie Alexander</td>
        <td>leslie.alexander@example.com</td>
        <td class="text-subtle">Admin</td>
      </tr>
      <tr>
        <td class="font-medium">Michael Foster</td>
        <td>michael.foster@example.com</td>
        <td class="text-subtle">Owner</td>
      </tr>
      <tr>
        <td class="font-medium">Dries Vincent</td>
        <td>dries.vincent@example.com</td>
        <td class="text-subtle">Member</td>
      </tr>
    </tbody>
  </table>

  <div class="accordion" style="max-inline-size: 30rem;">
    <details name="my_accordion">
      <summary>Is it accessible?</summary>
      <p class="mbe-4 text-sm">Yes. It adheres to the WAI-ARIA design pattern.</p>
    </details>
    <details name="my_accordion">
      <summary>Is it styled?</summary>
      <p class="mbe-4 text-sm">Yes. It comes with default styles that matches the other components' aesthetic.</p>
    </details>
    <details name="my_accordion">
      <summary>Is it animated?</summary>
      <p class="mbe-4 text-sm">Yes. It's animated by default, but you can disable it if you prefer.</p>
    </details>
  </div>  

  <div class="flex justify-center">
    <dialog id="my_modal" class="dialog dialog--drawer">
      <h1 class="text-lg font-semibold">Are you absolutely sure?</h1>
      <p class="text-sm text-subtle mbs-2">This action cannot be undone. This will permanently delete your account and remove your data from our servers.</p>

      <div class="flex gap-small justify-end mbs-4">
        <form method="dialog"><button class="btn btn--outline">Cancel</button></form>
        <button class="btn btn--primary">Continue</button>
      </div>
    </dialog>
    <button class="btn" onclick="my_modal.showModal();">Show modal</button>
  </div>
</div>
```
</details>

## Customization

### Root level

```css
:root {
  --color-bg: white;
  --color-text: var(--zinc-950);
  --color-text-reversed: white;
  --color-text-subtle: var(--zinc-500);
  --color-border: var(--zinc-200);
}
```

### Class level

```css
.btn--colored {
  --btn-background: var(--cyan-500);
  --btn-color: var(--cyan-950);
}
```

### Style level

```html
<button class="btn" style="--btn-background: #67e8f9; --btn-color: #083344;">
  Colored button
</button>
```

## Development

To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and the created tag, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/lazaronixon/css-zero. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [code of conduct](https://github.com/lazaronixon/css-zero/blob/master/CODE_OF_CONDUCT.md).

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the CSS Zero project's codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/lazaronixon/css-zero/blob/master/CODE_OF_CONDUCT.md).
