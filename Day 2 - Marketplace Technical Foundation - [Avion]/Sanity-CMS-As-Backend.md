● Sanity CMS as Backend:

• I will use sanity CMS as a database for my marketplace,
It will store data such as:

1. Products,
2. Orders Records,
3. Customers Details,
4. Transactions Records,
5. Shipment Records,


• [🏷️ Products Schema]:

import { defineType, defineField } from "sanity";

export default defineType({
  name: "product",
  title: "Product",
  type: "document",
  fields: [
    defineField({
      name: "id",
      title: "ID",
      type: "string",
      description: "A unique identifier for the product.",
    }),
    defineField({
      name: "name",
      title: "Product Name",
      type: "string",
      description: "The name of the product.",
    }),
    defineField({
      name: "price",
      title: "Price",
      type: "string",
      description: "The price of the product.",
    }),
    defineField({
      name: "images",
      title: "Product Images",
      type: "array",
      of: [{ type: "image" }],
      description: "Images of the product.",
    }),
    defineField({
      name: "ratings",
      title: "Ratings",
      type: "number",
      description: "The average ratings of the product (e.g., '5.0').",
    }),
    defineField({
      name: "tags",
      title: "Tags",
      type: "array",
      of: [{ type: "string" }],
      description: "Tags to categorize the product (e.g., 'Best Selling').",
    }),
    defineField({
      name: "discountPercentage",
      type: "number",
      title: "Discount Percentage",
    }),
    defineField({
      name: "priceWithoutDiscount",
      type: "number",
      title: "Price Without Discount",
      description: "Original price before discount",
    }),
    defineField({
      name: "ratingCount",
      type: "number",
      title: "Rating Count",
      description: "Number of ratings",
    }),
    defineField({
      name: "description",
      title: "Description",
      type: "text",
      description: "A detailed description of the product.",
    }),
    defineField({
      name: "variations",
      title: "Product Variations",
      type: "array",
      of: [
        defineField({
          name: "variation",
          type: "object",
          fields: [
            {
              name: "color",
              title: "Color",
              type: "string",
              description: "Color of the product variation.",
            },
            {
              name: "size",
              title: "Size",
              type: "string",
              description: "Size of the product variation.",
            },
            {
              name: "quantity",
              title: "Quantity",
              type: "number",
              description: "Available quantity for this variation.",
            },
          ],
        }),
      ],
      description: "List of variations for the product, including size, color, and quantity.",
    }),
  ],
});

• [🤝 Customer Schema]: 


import { defineType, defineField } from 'sanity'

export default defineType({
  name: 'customer',
  title: 'Customer',
  type: 'document',
  fields: [
    defineField({
        name: 'customerId',
        title: 'Customer ID',
        type: 'string',
        readOnly: true,
    }),
    defineField({
      name: 'name',
      title: 'Name',
      type: 'string',
    }),
    defineField({
      name: 'email',
      title: 'Email',
      type: 'string',
    }),
    defineField({
      name: 'phone',
      title: 'Phone',
      type: 'string',
    }),
    defineField({
      name: 'address',
      title: 'Address',
      type: 'object',
      fields: [
        { name: 'street', type: 'string', title: 'Street' },
        { name: 'city', type: 'string', title: 'City' },
        { name: 'state', type: 'string', title: 'State' },
        { name: 'zipCode', type: 'string', title: 'Zip Code' },
        { name: 'country', type: 'string', title: 'Country' },
      ],
    }),
  ],
});


• [📝 Order Schema]:

import { defineType, defineField } from 'sanity'

export default defineType({
  name: 'order',
  title: 'Order',
  type: 'document',
  fields: [
    defineField({
      name: 'orderId',
      title: 'Order ID',
      type: 'string',
    }),
    defineField({
      name: 'customer',
      title: 'Customer',
      type: 'reference',
      to: [{ type: 'customer' }],
    }),
    defineField({
      name: 'items',
      title: 'Items',
      type: 'array',
      of: [{ type: 'reference', to: [{ type: 'product' }] }],
    }),
    defineField({
      name: 'totalAmount',
      title: 'Total Amount',
      type: 'number',
    }),
    defineField({
      name: 'status',
      title: 'Order Status',
      type: 'string',
      options: {
        list: [
          { title: 'Pending', value: 'pending' },
          { title: 'Processing', value: 'processing' },
          { title: 'Shipped', value: 'shipped' },
          { title: 'Delivered', value: 'delivered' },
        ],
      },
    }),
    defineField({
      name: 'shippingAddress',
      title: 'Shipping Address',
      type: 'object',
      fields: [
        { name: 'street', type: 'string', title: 'Street' },
        { name: 'city', type: 'string', title: 'City' },
        { name: 'state', type: 'string', title: 'State' },
        { name: 'zipCode', type: 'string', title: 'Zip Code' },
        { name: 'country', type: 'string', title: 'Country' },
      ],
    }),
    defineField({
      name: "shipment",
      title: "Shipment",
      type: "reference",
      to: [{ type: "shipment" }], // Reference to shipment schema
    }),
  ],
})



• [🚚 Shipment Schema]:

import { defineType, defineField } from 'sanity'

export default defineType({
  name: 'shipment',
  title: 'Shipment',
  type: 'document',
  fields: [
    defineField({
      name: 'tracking_id',
      title: 'Tracking ID',
      type: 'string',
    }),
    defineField({
      name: "order",
      title: "Order",
      type: "reference",
      to: [{ type: "order" }], // Reference to order schema
    }),
    defineField({
      name: 'shipment_status',
      title: 'Shipment Status',
      type: 'string',
      options: {
        list: [
          { title: 'Pending', value: 'pending' },
          { title: 'In Transit', value: 'in_transit' },
          { title: 'Delivered', value: 'delivered' },
        ],
      },
    }),
    defineField({
      name: 'estimated_delivery_date',
      title: 'Estimated Delivery Date',
      type: 'date',
    }),
    defineField({
      name: 'carrier',
      title: 'Carrier',
      type: 'string',
    }),
    defineField({
      name: 'shipment_origin',
      title: 'Shipment Origin',
      type: 'string',
    }),
    defineField({
      name: 'shipment_destination',
      title: 'Shipment Destination',
      type: 'string',
    }),
    defineField({
      name: "customer",
      title: "Customer",
      type: "reference",
      to: [{ type: "customer" }], // Reference to customer schema
    }),
  ],
})





• [💳 Transaction Schema]:


export default {
    name: 'transaction',
    type: 'document',
    title: 'Transaction',
    fields: [
       {
        name: "order",
        type: "reference",
        to: [{ type: "order" }], // Reference to order schema
        title: "Order",
        description: "The order associated with this transaction",
      },
      {
        name: 'user',
        type: 'reference',
        to: [{ type: 'customer' }], // Reference to a customer schema
        title: 'User',
        description: 'User who made the transaction',
      },
      {
        name: 'productDetails',
        type: 'array',
        of: [{ type: 'reference', to: [{ type: 'product' }] }], // Reference to a product schema
        title: 'Product Details',
        description: 'Products purchased in the transaction',
      },
      {
        name: 'amount',
        type: 'number',
        title: 'Amount',
        description: 'Total amount of the transaction',
      },
      {
        name: 'paymentStatus',
        type: 'string',
        title: 'Payment Status',
        options: {
          list: [
            { title: 'Success', value: 'success' },
            { title: 'Pending', value: 'pending' },
            { title: 'Failed', value: 'failed' },
          ],
        },
      },
      {
        name: 'transactionDate',
        type: 'datetime',
        title: 'Transaction Date',
      },
    ],
  };
  
  




● Summary of Schema Relationships:

• Product:
Referenced by order and transaction.

• Customer:
Referenced by order, shipment, and transaction.

• Order:
References customer, product, and shipment.
Referenced by shipment and transaction.

• Shipment:
References order and customer.

• Transaction:
References order, customer, and product.