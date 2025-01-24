Below is a revised `README.md` that is more explicit about the requirements and project context but still leaves room for problem-solving. Feel free to adjust any wording or formatting to suit your style.

---

# Next.js Technical Test

Welcome to the MyDeal Product Detail Page (PDP) technical test. This simplified PDP shows how product information is structured and displayed on MyDeal.

## Getting Started

1. **Install Dependencies**
   ```bash
   yarn
   ```
2. **Run the Development Server**
   ```bash
   yarn dev
   ```
   The application should now be available at [http://localhost:3000](http://localhost:3000).

## Project Overview

This sample application is built with [Next.js](https://nextjs.org/) and demonstrates the following:

- **Basic Product Data**  
  A single “product” with details such as title, description, rating, images, etc. (see `services/products.ts` for the data).
- **Variants & Variant Options**  
  Products can have different sizes, colors, etc. Each _Variant_ (e.g. “Single - Black”) corresponds to a combination of _Variant Options_ (e.g. “Size: Single”, “Colour: Black”).

### Relevant Files

- **`@/services/products.ts`**  
  Contains the product data, including its variants and variant options.
- **`@/types/product.ts`**  
  Defines the TypeScript interfaces for products, images, variants, and so on.
- **`@/components/product-details.tsx`**  
  Displays the product details and a simple carousel of images.

## Your Task

1. **Add Select Dropdowns**  
   Each _Variant Option_ (e.g., “Size”, “Colour”) needs to have a corresponding [Select component](https://ui.shadcn.com/docs/components/select) for user selection. You’ll find the variant options in the `variantOptions` array.

> [!IMPORTANT]
> We use shadcn/ui components as our component library. You are expected to use the shadcn/ui Select component for this: https://ui.shadcn.com/docs/components/select

2. **Synchronize Selection with the Product Variant**

   - When users choose values for _all_ variant options, you should determine which _Variant_ matches that selection.
   - Once a specific variant is identified:
     - Update the **price** displayed on the page to reflect that variant’s price (if you decide to store variant-specific pricing).
     - Update the **carousel image** to match the selected variant (you’ll find the relevant image index in each variant).

3. **Handle Out-of-Stock Variants**  
   Some variants are marked as `outOfStock`. Decide how you want to handle or indicate this in your UI. For instance, you might disable their Select options or show a label.

4. **Keep it User-Friendly**  
   We want a minimal yet clear UI that lets users see how changing the Select options impacts the price and the displayed image.

## Expectations

- **Only Client-Side Code**
  The scope of the project is entirely limited to client-side components.
- **Code Quality & Clarity**  
  We’re looking for clean, well-structured, and readable code. Comments are welcome if something needs extra explanation.
- **Prettier**
  At MyDeal we use Prettier to format our code. Please make sure you have Prettier running locally to format all your code automatically.
- **No Extra-Dependencies**
  You shouldn't need to install anything on top of what's already in the project.

## Tips & Suggestions

- Familiarize yourself with `variantOptions` and `variants`. Each `variant` has a list of `variantOptionIds` that must match your user’s selections.
- Take note of the `imageIndex` property in each variant, which maps to the correct product image in the `images` array.
- Feel free to rearrange or refactor the project structure if you see fit. Just ensure it’s easy for us to follow your code.
