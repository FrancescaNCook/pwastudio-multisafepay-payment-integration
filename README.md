<p align="center">
  <img src="https://www.multisafepay.com/img/multisafepaylogo.svg" width="400px" position="center">
</p>

<p align="center">
  <img src="https://docs.multisafepay.com/logo/Plugins/Magento_PWA.svg" width="400px" height="120px" position="center">
</p>

# MultiSafepay extension for PWA Studio (Venia)
This extension for PWA Studio uses our Magento 2 plugin as a backend system. The plugin is fully compatible with Venia.

## About MultiSafepay 

MultiSafepay is a collecting payment service provider, which means we take care of electronic contracts, technical details, and payment collection for each payment method. You can start selling online today and manage all your transactions in one place.

## Supported payment methods
See [PWA Studio (Venia)](https://docs.multisafepay.com/docs/pwa-studio-venia) > Payment methods.

**Note:** This extension does not support Request To Pay, Direct Debit, E-invoicing, or Pay After Delivery. You can implement these methods using the iDEAL, AfterPay, or in3 components of the plugin.

## Prerequisites

- You will need a [MultiSafepay account](https://testmerchant.multisafepay.com/signup). Consider a test account first.
- To support GraphQL queries, install the <a href="https://github.com/MultiSafepay/magento2-graphql" target="_blank">MultiSafepay Magento 2 GraphQL plugin</a>.
- You must also meet Magento's requirements for PWA Studio (Venia). See Magento – <a href="https://magento.github.io/pwa-studio/venia-pwa-concept/setup/#prerequisites" target="_blank">Prerequisites</a>
- [Open Software License (OSL 3.0)](https://github.com/MultiSafepay/Magento2Msp/blob/master/LICENSE.md)

## Installation

1. Install the MultiSafepay plugin for supporting GraphQL queries, which includes the MultiSafepay Core, Frontend and Adminhtml plugins. For instructions, see MultiSafepay GitHub – <a href="https://github.com/MultiSafepay/magento2-graphql" target="_blank">Magento 2 GraphQL</a>.    
2. Configure the payment methods and your API keys in the Magento admin panel.
3. To configure the URLs for your success and cancellation pages, go to **Stores** > **Configuration** > **MultiSafepay** > **General settings** > **Advanced settings** > **Use custom return urls for PWA storefront integration**.
    - For **Custom redirect URL after canceling the payment**, we recommend using: *<your_pwa_url>/cart?maskedId={{quote.masked_id}}&multisafepayRestore=true*
    - For the **Custom success page URL**, we recommend using: *<your_pwa_url>/multisafepay/checkout/success/{{order.increment_id}}/maskedId/{{quote.masked_id}}*
4. Install Venia storefront. For instructions, see Magento GitHub – <a href="https://magento.github.io/pwa-studio/venia-pwa-concept/setup/" target="_blank">Venia PWA concept</a>.
    - Go to the extension folder:
   ```bash 
   cd your_project/packages/extensions
   ```
   - Create a MultiSafepay extension folder:
   ```bash 
   mkdir multisafepay-payment-integration
   ```
   - Clone all extension files from this repository in the **multisafepay-payment-integration** folder.
   - Link the extension in **venia-concept package.json**.   
   - Go to the **venia-concept** folder and open **package.json**:
   
   ```bash 
   cd your_project/packages/venia-concept
   ```
   
   - Add the next dependency:
   
   ```bash 
   "dependencies": {
        "@multisafepay/multisafepay-payment-integration": "link:../extensions/multisafepay-payment-integration"
    },
   ```
   
   - Go back to the project root folder and execute the following commands:
   ```bash 
   yarn install && yarn watch:venia
   ```
5. Explore the checkout in your Venia application:
 <img width="1000" alt="Screenshot 2021-03-25 at 12 56 46" src="https://user-images.githubusercontent.com/78361324/112469889-4a728100-8d6a-11eb-98dd-7429f1154952.png">

## Support

- Create an issue on this repository. 
- Email <a href="mailto:integration@multisafepay.com">integration@multisafepay.com</a>
- Start a conversation on our Magento Slack channel: [#multisafepay-payments](https://magentocommeng.slack.com/messages/multisafepay-payments/).

## Contributors

If you see an opportunity to make an improvement, we invite you to create a pull request, create an issue, or email <integration@multisafepay.com> 

As a thank you for your contribution, we'll send you a MultiSafepay t-shirt, making you part of the team!

## Want to be part of the team?

Are you a developer interested in working at MultiSafepay? Check out our [job openings](https://www.multisafepay.com/careers/#jobopenings) and feel free to get in touch!
