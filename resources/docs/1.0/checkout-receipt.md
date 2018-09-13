# Displaying and emailing the order receipt

---

<a name="section-1"></a>

You probably want to display a confirmation or even a full receipt when the user has successfully placed an order.  
The url to the order confirmation is automatically returned from the `checkout/charge` endpoint, and the view you configured in your `templates.order-confirmation` will be displayed on this route. The view has access to the full `$order` object.

### Emailing a receipt
If you've enabled the `mail.customer.order_placed` setting, an email will automatically be sent to the customer when they place an order. This email has access to the same `$order` object, so you could use the same view partial for both the order confirmation view and the email if you'd like.  
If you haven't configured a template for this email, a default template will be used.
