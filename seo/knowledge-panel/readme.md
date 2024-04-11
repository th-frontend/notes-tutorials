# Schema for Knowledge Panel

## Usage Warning

This snippet needs to be modified for each company you set it up for. It is not a one-size-fits-all solution.

## Schema Markup

The provided code snippet is a JSON-LD (JavaScript Object Notation for Linked Data) schema markup that can be used to generate a knowledge panel for a company's about page. The schema follows the [schema.org](https://schema.org/) vocabulary.

### Key Elements

1. `@context`: Specifies the URL of the schema.org vocabulary used.
2. `@type`: Indicates the type of entity being described, in this case, an `AboutPage`.
3. `id`: The URL of the about page being described.
4. `mainEntityOfPage`: The URL of the main website.
5. `isPartOf`: Specifies that this about page is part of a larger website.
6. `lastReviewed`: The date when the information was last reviewed.
7. `reviewedBy`: The corporation that reviewed the information.
8. `audience`: The intended audience for the about page (not specified in the example).
9. `name`: The name of the about page.
10. `about`: Provides detailed information about the company, including:
    - `@type`: Specifies the type of entity, in this case, a `Corporation`.
    - `id`: A unique identifier for the corporation.
    - `description`: A detailed description of the company and its services.
    - `name`: The company's name.
    - `url`: The company's website URL.
    - `mainEntityOfPage`: The main URL of the company's website.
    - `sameAs`: URLs of the company's profiles on various online platforms.
    - `additionalType`: Additional information about the company's field of work.
    - `image`: URLs of the company's logo (not specified in the example).
    - `alternateName`: Alternate names for the company.
    - `legalName`: The company's legal name.
    - `logo`: The URL of the company's logo.
    - `address`: The company's physical address.
    - `location`: The company's location.
    - `founder`: Information about the company's founder.
    - `award`: Any awards the company has received (not specified in the example).
    - `employee`: Information about the company's employees (not specified in the example).
    - `subOrganization`: Information about any sub-organizations of the company (not specified in the example).
    - `contactPoint`: Information about how to contact the company (not specified in the example).
    - `disambiguatingDescription`: Additional information to help distinguish the company from other entities.

## Usage

To use this schema markup, you would typically include the JSON-LD code within the `<head>` section of your HTML document, as shown in the example. This allows search engines and other applications to parse and understand the structured data about your company's about page.

Remember to modify the code snippet for each company you set it up for, as the information will be specific to each organization.


```js
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "AboutPage",
    "id": "https://www.basementsystems.com/company.html",
    "mainEntityOfPage": "https://www.basementsystems.com/",
    "isPartOf": {
      "@type": "WebSite",
      "id": "https:///#website"
    },
    "lastReviewed": "2023-08-25 18:51:11",
    "reviewedBy": {
      "@type": "Corporation",
      "name": "Basement Systems",
      "url": "https://www.basementsystems.com/"
    },
    "audience": [],
    "name": "About Basement Systems",
    "about": {
      "@type": "Corporation",
      "id": "https://www.basementsystems.com/company.html/#/schema/corporation/4f38108bdab5a435",
      "description": "About Basement Systems, Waterproofing company. Basement Systems Inc. , based in Seymour, Connecticut, is a network of basement waterproofing and crawl space repair contractors spanning across the United States and Canada. Since 1987, their innovative products and systems have helped homeowners transform their wet, leaky basements and nasty crawl spaces into dry, healthy living spaces. Services: Basement Systems Inc. specializes in basement waterproofing using quality products from the Basement Systems Inc. line. The company designs customized systems to keep basements dry and healthy and offers a complete range of services from consultation to installation and maintenance. Contractors in this exclusive network offer a variety of basement waterproofing and crawl space repair products, including French drains, sump pumps, dehumidifiers, and so much more. Coverage: Basement Systems Inc. has over 150 local waterproofers across the United States and Canada. The company has a wide coverage area, with contractors located in many states and regions, including Connecticut, New Hampshire, Ohio, Indiana, and Georgia. Customer Satisfaction: Basement Systems Inc. prides itself on going above and beyond to make sure customers are happy with their products and services. From the first phone call to the installation and maintenance, the company is committed to providing excellent customer service and ensuring that homes stay dry and healthy. Basement Systems Inc. has been in business since 1987 and has built a reputation for honesty, integrity, and high-quality workmanship. The company is a leader in dry, below-grade space products and has a network of affiliated contractors across the United States, Canada, and the UK. Basement Systems Inc. offers a competitive lifetime warranty that is transferable to the next owner of the home.",
      "name": "Basement Systems",
      "url": "https://www.basementsystems.com/",
      "mainEntityOfPage": "https://www.basementsystems.com/",
      "sameAs":
["https://www.bbb.org/us/ct/seymour/profile/basement-waterproofing/basement-systems-inc-0111-87118487", "https://www.linkedin.com/company/basement-systems-inc-",
                  "https://twitter.com/basementsystems", "https://www.facebook.com/basementsystemsinc/",
                 "https://www.youtube.com/c/BasementSystemsInc", "https://www.crunchbase.com/organization/basement-systems-inc", "https://www.pinterest.com/basementsystems/", "https://www.google.com/search?kgmid=/g/11g1lgr5p_"],
      "additionalType": "https://en.wikipedia.org/wiki/Basement_waterproofing",
      "image": [],
      "alternateName": ["Basement Systems", "Inc."],
      "legalName": "Basement Systems, Inc.",
      "logo": "https://cdn.treehouseinternetgroup.com/cms_images/215/bs-logo-2018.svg",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "60 Silvermine Road",
        "addressLocality": "Seymour",
        "postalCode": "06483",
        "addressCountry": "US"
      },
      "location": {
        "@type": "Place",
        "address": {
          "@type": "PostalAddress",
          "streetAddress": "60 Silvermine Road",
          "addressLocality": "Seymour",
          "postalCode": "06483",
          "addressCountry": "US"
        }
      },
    
      "founder": [{
        "@type": "Person",
        "name": "Larry Janesky",
        "url": "http://www.larryjanesky.com/"
      }],
      "award": [],
      "employee": [],
      "subOrganization": [],
      "contactPoint": [],
      "disambiguatingDescription": "Basement Systems: Waterproofing company.  The legal name for Basement Systems is Basement Systems, Inc.. Basement Systems was founded by Larry Janesky, "
    }
  }
</script>
```
