> **BrainSync Context Pumper** 🧠
> Dynamically loaded for active file: `snippets/structured-data-jewelry.liquid` (Domain: **Generic Logic**)

### 📐 Generic Logic Conventions & Fixes
- **[what-changed] Replaced auth SIHO**: -   SIHO CPH Advanced Structured Data
+   SIHO CPH Advanced Structured Data - Comprehensive SEO Schema
- {% endcomment %}
+   Supports: JewelryStore, WebSite, Product, Collection, Article, FAQ, Breadcrumb
- 
+ {% endcomment %}
- {% if request.page_type == 'index' %}
+ 
-   <script type="application/ld+json">
+ {%- comment -%}=== HOMEPAGE: JewelryStore + WebSite + Organization ==={%- endcomment -%}
-     {
+ {% if request.page_type == 'index' %}
-       "@context": "https://schema.org",
+   <script type="application/ld+json">
-       "@type": "JewelryStore",
+     {
-       "name": "{{ shop.name }}",
+       "@context": "https://schema.org",
-       "url": "{{ shop.url }}",
+       "@type": "JewelryStore",
-       {% if settings.logo != blank %}
+       "name": "{{ shop.name }}",
-         "logo": "{{ settings.logo | image_url: width: 500 }}",
+       "url": "{{ shop.url }}",
-       {% endif %}
+       {% if settings.logo != blank %}
-       "description": "{{ shop.description | escape }}",
+         "logo": "https:{{ settings.logo | image_url: width: 500 }}",
-       "address": {
+         "image": "https:{{ settings.logo | image_url: width: 1200 }}",
-         "@type": "PostalAddress",
+       {% endif %}
-         "addressLocality": "Copenhagen",
+       "description": "{{ shop.description | escape | default: 'Elegante smykker i 925 sterling sølv og 18K guld. Dansk design fra København.' }}",
-         "addressCountry": "DK"
+       "telephone": "{{ settings.social_twitter_link | default: '' }}",
-       },
+       "priceRange": "$$",
-       "sameAs": [
+       "currenciesAccepted": "DKK",
-         "{{ settings.social_instagram_link }}",
+       "paymentAccepted": "Kreditkort, MobilePay, Visa, Mastercard",
-         "{{ settings.social_facebook_link }}"
+       "address": {
-       ]
+         "@type": "PostalAddress",
-     }
+         "addressLocality": "København",
-   </script>
+         "addressRegion": "Hovedstaden",
- {% endif %}
+         "addressCountr
… [diff truncated]
- **[trade-off] trade-off in jewelry-icons.liquid**: -   SIHO CPH Jewellery Icons - Horizon Native
+   SIHO CPH Jewellery Icons - Elegant & Refined
-       <circle cx="12" cy="12" r="9" stroke="currentColor" stroke-width="1.5"/>
+       <circle cx="12" cy="12" r="9" stroke="currentColor" stroke-width="1.25"/>
-       <path d="M12 7V17M7 12H17" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
+       <path d="M8.5 12.5C8.5 12.5 10 15 12 15C14 15 15.5 12.5 15.5 12.5" stroke="currentColor" stroke-width="1.25" stroke-linecap="round"/>
-       <path d="M15.5 8.5L8.5 15.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
+       <text x="12" y="10.5" text-anchor="middle" fill="currentColor" font-size="5" font-weight="600" font-family="system-ui">925</text>
-       <rect x="5" y="7" width="14" height="10" rx="1" stroke="currentColor" stroke-width="1.5"/>
+       <rect x="4" y="8" width="16" height="8" rx="2" stroke="currentColor" stroke-width="1.25"/>
-       <path d="M9 10L12 13L15 10" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
+       <path d="M8 8V6a4 4 0 0 1 8 0v2" stroke="currentColor" stroke-width="1.25" stroke-linecap="round"/>
-     </svg>
+       <circle cx="12" cy="12" r="1.5" fill="currentColor" opacity="0.6"/>
-   {% when 'diamond' %}
+     </svg>
-     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
+   {% when 'diamond' %}
-       <path d="M12 3L20 9L12 21L4 9L12 3Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
+     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
-       <path d="M4 9H20" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
+       <path d="M12 2L4 9L12 22L20 9L12 2Z" stroke="currentColor" stroke-width="1.25" stroke-linejoin="round"/>
-       <path d="M8 9L12 21L16 9" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-l
… [diff truncated]
- **[decision] Optimized Tidl**: -   assign og_description = page_description | default: shop.description | default: "Tidløse og elegante smykker i 925 sterling sølv og 18K guld. Køb armbånd, halskæder og øreringe hos SIHO CPH."
+   assign og_description = page_description | default: shop.description | default: "Tidløse og elegante smykker i 925 sterling sølv og 18K guld. Køb armbånd, halskæder, øreringe og ringe hos SIHO CPH. Dansk design, hurtig levering i Danmark."
-     assign og_title = product.title | append: " - " | append: brand_suffix
+     assign og_title = product.title | append: " | Køb online - SIHO CPH"
-     assign og_title = collection.title | append: " " | append: brand_suffix
+     assign og_title = collection.title | append: " | SIHO CPH - Smykker i sølv & guld"
-   elsif request.page_type == 'password'
+     assign og_title = article.title | append: " | SIHO CPH Blog"
-     assign og_url = request.origin
+   elsif request.page_type == 'blog'
-   endif
+     assign og_title = blog.title | append: " | SIHO CPH Smykkeblog"
- %}
+   elsif request.page_type == 'password'
- 
+     assign og_url = request.origin
- {%- if request.page_type == 'product' -%}
+   elsif request.page_type == 'search'
-   <link rel="preload" as="image" href="{{ product.featured_media | image_url: width: 1200 }}" fetchpriority="high">
+     assign og_title = "Søg i smykker | SIHO CPH"
- {%- endif -%}
+   endif
- 
+ -%}
- <meta
+ 
-   property="og:site_name"
+ {%- comment -%} Robots meta - control indexing {%- endcomment -%}
-   content="{{ shop.name }}"
+ {%- if request.page_type == 'search' or request.page_type == 'cart' or request.page_type == 'password' -%}
- >
+   <meta name="robots" content="noindex, nofollow">
- <meta
+ {%- elsif template contains 'customers' -%}
-   property="og:url"
+   <meta name="robots" content="noindex, nofollow">
-   content="{{ og_url }}"
+ {%- else -%}
- >
+   <meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1">
- <meta
+ {%
… [diff truncated]
- **[what-changed] what-changed in jewelry-icons.liquid**: - {% endcase %}
+   {% when 'care-brush' %}
- 
+     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
+       <path d="M6 18l4-4 4 4-4 4zM10 14l8-8M15 3l6 6" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
+     </svg>
+   {% when 'care-box' %}
+     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
+       <path d="M21 8v11a2 2 0 01-2 2H5a2 2 0 01-2-2V8M1 3h22v5H1V3zM10 12h4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
+     </svg>
+   {% when 'care-water' %}
+     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
+       <path d="M12 2.6L4.5 10c-3.3 3.3-3.3 8.7 0 12s8.7 3.3 12 0c3.3-3.3 3.3-8.7 0-12L12 2.6z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
+     </svg>
+ {% endcase %}
+ 
- **[what-changed] Updated schema main-collection**: -     {% content_for 'block',
+     {% render 'collection-seo-description', collection: collection %}
-       type: 'filters',
+ 
-       id: 'filters',
+     {% content_for 'block',
-       results: collection,
+       type: 'filters',
-       results_size: collection.products_count
+       id: 'filters',
-     %}
+       results: collection,
- 
+       results_size: collection.products_count
-     {% assign products_per_page = 24 %}
+     %}
-     {% if section.settings.enable_infinite_scroll == false %}
+     {% assign products_per_page = 24 %}
-       {% assign products_per_page = section.settings.products_per_page %}
+ 
-     {% endif %}
+     {% if section.settings.enable_infinite_scroll == false %}
- 
+       {% assign products_per_page = section.settings.products_per_page %}
-     {% paginate collection.products by products_per_page %}
+     {% endif %}
-       {% capture children %}
+ 
-         {% for product in collection.products %}
+     {% paginate collection.products by products_per_page %}
-           <li
+       {% capture children %}
-             id="{{ section.id }}-{{ product.id }}"
+         {% for product in collection.products %}
-             class="product-grid__item product-grid__item--{{ forloop.index0 }}"
+           <li
-             data-page="{{ paginate.current_page }}"
+             id="{{ section.id }}-{{ product.id }}"
-             data-product-id="{{ product.id }}"
+             class="product-grid__item product-grid__item--{{ forloop.index0 }}"
-             ref="cards[]"
+             data-page="{{ paginate.current_page }}"
-           >
+             data-product-id="{{ product.id }}"
-             {% # theme-check-disable %}
+             ref="cards[]"
-             {% content_for 'block', type: '_product-card', id: 'product-card', closest.product: product %}
+           >
-             {% # theme-check-enable %}
+             {% # theme-check-disable %}
-           </li>
+             {% content_for 'block', type: '_product
… [diff truncated]
- **[what-changed] Updated schema Tablet**: -   <div class="jewelry-care-grid">
+   <div class="jewelry-care">
-     <div class="jewelry-care-header">
+     <div class="jewelry-care__header">
-       <h2 class="h2">{{ section.settings.title | escape }}</h2>
+       <h2 class="jewelry-care__title h3">{{ section.settings.title | escape }}</h2>
-       <p class="paragraph--large">{{ section.settings.subtitle | escape }}</p>
+       <p class="jewelry-care__subtitle">{{ section.settings.subtitle | escape }}</p>
-     <div class="care-tips-grid">
+     <div class="jewelry-care__grid">
-         <div class="care-tip-item" {{ block.shopify_attributes }}>
+         <div class="jewelry-care__tip" {{ block.shopify_attributes }}>
-           <h3 class="h6 care-tip-title">
+           <div class="jewelry-care__tip-icon svg-wrapper">
-             <span class="care-tip-icon svg-wrapper">
+             {%- render 'jewelry-icons', icon: block.settings.icon_type -%}
-               {%- render 'jewelry-icons', icon: block.settings.icon_type -%}
+           </div>
-             </span>
+           <h3 class="jewelry-care__tip-title">{{ block.settings.title | escape }}</h3>
-             {{ block.settings.title | escape }}
+           <p class="jewelry-care__tip-text">{{ block.settings.text | escape }}</p>
-           </h3>
+         </div>
-           <p class="care-tip-text paragraph--small">{{ block.settings.text | escape }}</p>
+       {%- endfor -%}
-         </div>
+     </div>
-       {%- endfor -%}
+   </div>
-     </div>
+ {%- endcapture -%}
-   </div>
+ 
- {%- endcapture -%}
+ {%- render 'section', section: section, children: children -%}
- {%- render 'section', section: section, children: children -%}
+ <style>
- 
+   .jewelry-care {
- <style>
+     width: 100%;
-   /* ... (styles remain the same) ... */
+   }
- </style>
+ 
- 
+   .jewelry-care__header {
- {% schema %}
+     text-align: center;
- {
+     margin-block-end: 48px;
-   "name": "SIHO Smykkepleje",
+     max-width: 600px;
-   "class": "section-wrapper",
+  
… [diff truncated]
- **[what-changed] Updated schema Tablet**: -   <div class="trust-signals-grid">
+   <div class="trust-signals">
-       <div class="trust-signal-item" {{ block.shopify_attributes }}>
+       <div class="trust-signal" {{ block.shopify_attributes }}>
-         <div class="trust-signal-icon svg-wrapper">
+         <div class="trust-signal__icon-wrap">
-           {%- render 'jewelry-icons', icon: block.settings.icon_type -%}
+           <div class="trust-signal__icon svg-wrapper">
-         </div>
+             {%- render 'jewelry-icons', icon: block.settings.icon_type -%}
-         <div class="trust-signal-content">
+           </div>
-           <h3 class="trust-signal-title">{{ block.settings.title | escape }}</h3>
+         </div>
-           <p class="trust-signal-text">{{ block.settings.text | escape }}</p>
+         <div class="trust-signal__content">
-         </div>
+           <h3 class="trust-signal__title">{{ block.settings.title | escape }}</h3>
-       </div>
+           <p class="trust-signal__text">{{ block.settings.text | escape }}</p>
-     {%- endfor -%}
+         </div>
-   </div>
+       </div>
- {%- endcapture -%}
+     {%- endfor -%}
- 
+   </div>
- {%- render 'section', section: section, children: children -%}
+ {%- endcapture -%}
- <style>
+ {%- render 'section', section: section, children: children -%}
-   .trust-signals-grid {
+ 
-     display: flex;
+ <style>
-     flex-wrap: wrap;
+   .trust-signals {
-     justify-content: center;
+     display: grid;
-     gap: var(--gap-md);
+     grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
-     width: 100%;
+     gap: 1px;
-   }
+     width: 100%;
- 
+     background: rgba(var(--color-foreground-rgb), 0.06);
-   .trust-signal-item {
+     border-radius: calc(var(--style-border-radius) + 4px);
-     flex: 1;
+     overflow: hidden;
-     min-width: 250px;
+   }
-     display: flex;
+ 
-     align-items: center;
+   .trust-signal {
-     gap: var(--gap-sm);
+     display: flex;
-     padding: var(--padding-md);
+     align-items:
… [diff truncated]
- **[what-changed] Updated schema SIHO**: -   "name": "SIHO Jewellery Care",
+   "name": "SIHO Smykkepleje",
-     /* ... (settings remain same) ... */
+     {
-   ],
+       "type": "header",
-   "blocks": [
+       "content": "Layout"
-     {
+     },
-       "type": "tip",
+     {
-       "name": "Care Tip",
+       "type": "select",
-       "settings": [
+       "id": "section_width",
-         {
+       "label": "Bredde",
-           "type": "select",
+       "options": [
-           "id": "icon_type",
+         { "value": "page-width", "label": "Sidebredde" },
-           "label": "Icon Type",
+         { "value": "full-width", "label": "Fuld bredde" }
-           "options": [
+       ],
-             { "value": "care-brush", "label": "Cleaning Brush" },
+       "default": "page-width"
-             { "value": "care-box", "label": "Jewellery Box" },
+     },
-             { "value": "care-water", "label": "Water/Cleaning" },
+     {
-             { "value": "waterproof", "label": "Waterproof" },
+       "type": "header",
-             { "value": "silver", "label": "Silver Care" }
+       "content": "Udseende"
-           ],
+     },
-           "default": "care-brush"
+     {
-         },
+       "type": "color_scheme",
-         {
+       "id": "color_scheme",
-           "type": "text",
+       "label": "Farveskema",
-           "id": "title",
+       "default": "scheme-1"
-           "label": "Tip Title",
+     },
-           "default": "Undgå kemikalier"
+     {
-         },
+       "type": "text",
-         {
+       "id": "title",
-           "type": "textarea",
+       "label": "Titel",
-           "id": "text",
+       "default": "Pas godt på dine smykker"
-           "label": "Tip Text",
+     },
-           "default": "Tag dine smykker af når du bruger parfume, lotion eller hårspray."
+     {
-         }
+       "type": "text",
-       ]
+       "id": "subtitle",
-     }
+       "label": "Undertitel",
-   ],
+       "default": "Følg disse enkle trin for at bevare glansen i dine SIHO CPH smyk
… [diff truncated]
- **[what-changed] Updated schema SIHO**: -               {{- 'icon-checkmark-burst.svg' | inline_asset_content -}}
+               {%- render 'jewelry-icons', icon: block.settings.icon_type -%}
-   .jewelry-care-header {
+   /* ... (styles remain the same) ... */
-     text-align: center;
+ </style>
-     max-width: 700px;
+ 
-     margin: 0 auto 50px;
+ {% schema %}
-     display: flex;
+ {
-     flex-direction: column;
+   "name": "SIHO Jewellery Care",
-     gap: 12px;
+   "class": "section-wrapper",
-   }
+   "settings": [
- 
+     /* ... (settings remain same) ... */
-   .care-tips-grid {
+   ],
-     display: grid;
+   "blocks": [
-     grid-template-columns: repeat(2, 1fr);
+     {
-     gap: 40px;
+       "type": "tip",
-     width: 100%;
+       "name": "Care Tip",
-   }
+       "settings": [
- 
+         {
-   .care-tip-title {
+           "type": "select",
-     display: flex;
+           "id": "icon_type",
-     align-items: center;
+           "label": "Icon Type",
-     gap: 12px;
+           "options": [
-     margin-bottom: 8px;
+             { "value": "care-brush", "label": "Cleaning Brush" },
-     font-weight: 600;
+             { "value": "care-box", "label": "Jewellery Box" },
-   }
+             { "value": "care-water", "label": "Water/Cleaning" },
- 
+             { "value": "waterproof", "label": "Waterproof" },
-   .care-tip-icon {
+             { "value": "silver", "label": "Silver Care" }
-     color: var(--color-foreground);
+           ],
-     width: 24px;
+           "default": "care-brush"
-     height: 24px;
+         },
-     opacity: 0.8;
+         {
-   }
+           "type": "text",
- 
+           "id": "title",
-   .care-tip-text {
+           "label": "Tip Title",
-     margin: 0;
+           "default": "Undgå kemikalier"
-     line-height: 1.6;
+         },
-     opacity: 0.85;
+         {
-   }
+           "type": "textarea",
- 
+           "id": "text",
-   @media screen and (max-width: 749px) {
+           "label": "Tip Text",
-     .care-tips-grid {
+           "
… [diff truncated]
- **[what-changed] Updated schema Specifikationer**: -   style="{% render 'spacing-style', settings: block_settings %}"
+   style="
-   {{ block.shopify_attributes }}
+     --summary-font-family: var(--font-{{ block_settings.type_preset }}--family);
- >
+     --summary-font-weight: var(--font-{{ block_settings.type_preset }}--weight);
-   <details class="jewelry-specs__details" {% if block_settings.open_by_default %}open{% endif %}>
+     --summary-font-size: var(--font-{{ block_settings.type_preset }}--size);
-     <summary class="jewelry-specs__summary h6">
+     --summary-font-case: var(--font-{{ block_settings.type_preset }}--case);
-       <span>{{ block_settings.heading | default: 'Specifikationer' }}</span>
+     {% render 'spacing-style', settings: block_settings %}
-       <span class="jewelry-specs__icon">
+   "
-         <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
+   {{ block.shopify_attributes }}
-           <path d="M5 7.5L10 12.5L15 7.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
+ >
-         </svg>
+   <details class="jewelry-specs__details" {% if block_settings.open_by_default %}open{% endif %}>
-       </span>
+     <summary class="jewelry-specs__summary">
-     </summary>
+       <span class="jewelry-specs__heading">{{ block_settings.heading | default: 'Specifikationer' }}</span>
-     <div class="jewelry-specs__content">
+       <span class="jewelry-specs__arrow svg-wrapper">
-       <ul class="jewelry-specs__list">
+         {{- 'icon-caret.svg' | inline_asset_content -}}
-         {% if block_settings.material != blank or product.metafields.custom.material != blank %}
+       </span>
-           <li class="jewelry-specs__item">
+     </summary>
-             <span class="jewelry-specs__label">Materiale:</span>
+     <div class="jewelry-specs__content">
-             <span class="jewelry-specs__value">
+       <div class="jewelry-specs__table">
-               {% if product.metafields.custom.materia
… [diff truncated]
