# OxyMinicart


This code  allows you to display an simple AJAX minicart in Oxygen Builder template. It display Cart Icon, Counter and Total with shop currency and it is linked to Woocommerce Shoping Cart section. No dropdowns or any fancy features, just a light fast and simple minicart that supports the AJAX add to cart option.

![oxyminicart](https://user-images.githubusercontent.com/1156059/156540426-b917725f-18eb-4060-b2ad-4b785d530734.jpg)


Installation:
--------------
--------------


1.Code Snippets
----------------

1. Install Code Snippets plugin (https://wordpress.org/plugins/code-snippets/).
2. Go to plugin and click "Add New" link.
3. Enter Title: OxyMinicart
4. Enter Code:
```
add_filter( 'woocommerce_add_to_cart_fragments', 'icon_minicart_count_fragments', 10, 1 );
function icon_minicart_count_fragments( $fragments ) {
   $fragments['div.minicount'] = '<div class="minicount">' . WC()->cart->get_cart_contents_count() . '</div>';
   $fragments['div.minitotal'] = '<div class="minitotal">' . WC()->cart->get_cart_total() . '</div>';
    return $fragments; 
}
```
5. Select "Only run on site front-end"
6. Click "Save Changes and Activate" button


2.Now let's add Reusable part in Oxygen Builder
-------------------------------------------------

1. Go to Oxygen > Templates and click "Add New Reusable Part"
2. Enter name: oxyminicart and click "Publish" button
3. Click "+Shortcodes" link
4. Enter this code:
```
[ct_link_2 ct_sign_sha256='e6d260046ca72c000a0dae1e66539f4bc0865cbe9b2871ec010892a8c63dd9fb' ct_options='{"ct_id":1,"ct_parent":0,"selector":"div_block-37-26","nicename":"Div (#37) Minicart","ct_depth":"2","original":{"target":"","width":"140","flex-direction":"row","display":"flex","height":"50","url_encoded":"true","globalconditions":{},"margin-left":"20","custom-attributes":{},"url":"/cart"},"media":{"phone-landscape":{"original":{"width":"60"}}}}'][ct_fancy_icon ct_sign_sha256='e1d3820a919012043baeda4866b1e8440cfb0c148b722c74ce733834ca7a9171' ct_options='{"ct_id":2,"ct_parent":1,"selector":"fancy_icon-50-26","original":{"icon-id":"Lineariconsicon-cart","icon-size":"30","icon-style":"3","icon-padding":"15","icon-color":"#4f6636"},"nicename":"Icon (#50) Cart","activeselector":false,"ct_depth":3}'][/ct_fancy_icon][ct_code_block ct_sign_sha256='fd806f9120216911c920f7a4137078b913897b8abd8088e35665e813ab462095' ct_options='{"ct_id":3,"ct_parent":1,"selector":"code_block-47-26","original":{"code-php":"PGRpdiBjbGFzcz0ibWluaWNvdW50Ij48P3BocCBlY2hvIFdDKCktPmNhcnQtPmdldF9jYXJ0X2NvbnRlbnRzX2NvdW50KCk7ID8+PC9kaXY+Cg==","background-color":"#1d95a5","color":"#ffffff","border-radius":"20","width":"23","height":"23","text-align":"center","align-items":"center","margin-top":"-28","margin-left":"-20","border-top-style":"none","border-right-style":"none","border-bottom-style":"none","border-left-style":"none","-webkit-font-smoothing":"antialiased","font-weight":"600","font-size":"14","line-height":"1.6"},"nicename":"Code Block (#47) Count","activeselector":false,"ct_depth":3}'][/ct_code_block][ct_code_block ct_sign_sha256='0cae81da57f71ad7829dcd95cf65cede0421fd90ed16fe9fd3b8a4bab7a2a22c' ct_options='{"ct_id":4,"ct_parent":1,"selector":"code_block-57-26","original":{"code-php":"PGRpdiBjbGFzcz0ibWluaXRvdGFsIj4KCTw/cGhwIAoJZWNobyBXQygpLT5jYXJ0LT5nZXRfY2FydF90b3RhbCgpOwoJPz4KPC9kaXY+","margin-left":"15","color":"#1883ad"},"nicename":"Code Block (#57) Total","activeselector":false,"ct_depth":3,"media":{"phone-landscape":{"original":{"display":"none"}}}}'][/ct_code_block][/ct_link_2]
```
5. Click "Update" button

3.Add OxyMinicart anywhere 
---------------------------

1. Open your main template (template which containing header section) in Oxygen Builder, select element in which you want to add minicart
2. Click Add > Reusable parts > OxyMinicart
3. Edit css to fit your needs


