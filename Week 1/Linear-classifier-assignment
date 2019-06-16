

```python
from __future__ import division
import graphlab
import math 
import string
```


```python
products = graphlab.SFrame('amazon_baby.gl/')
```

    This non-commercial license of GraphLab Create for academic use is assigned to jayantdahiya1999@gmail.com and will expire on May 27, 2020.
    

    [INFO] graphlab.cython.cy_server: GraphLab Create v2.1 started. Logging: C:\Users\JAYANT~1\AppData\Local\Temp\graphlab_server_1560657371.log.0
    


```python
products
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">name</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">review</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">rating</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Planetwise Flannel Wipes</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">These flannel wipes are<br>OK, but in my opinion ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">3.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Planetwise Wipe Pouch</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">it came early and was not<br>disappointed. i love ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Annas Dream Full Quilt<br>with 2 Shams ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Very soft and comfortable<br>and warmer than it ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Stop Pacifier Sucking<br>without tears with ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">This is a product well<br>worth the purchase.  I ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Stop Pacifier Sucking<br>without tears with ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">All of my kids have cried<br>non-stop when I tried to ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Stop Pacifier Sucking<br>without tears with ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">When the Binky Fairy came<br>to our house, we didn't ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">A Tale of Baby's Days<br>with Peter Rabbit ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Lovely book, it's bound<br>tightly so you may no ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">4.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Baby Tracker&amp;reg; - Daily<br>Childcare Journal, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Perfect for new parents.<br>We were able to keep ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Baby Tracker&amp;reg; - Daily<br>Childcare Journal, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">A friend of mine pinned<br>this product on Pinte ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Baby Tracker&amp;reg; - Daily<br>Childcare Journal, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">This has been an easy way<br>for my nanny to record ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">4.0</td>
    </tr>
</table>
[183531 rows x 3 columns]<br/>Note: Only the head of the SFrame is printed.<br/>You can use print_rows(num_rows=m, num_columns=n) to print more rows and columns.
</div>




```python
products[270]
```




    {'name': 'The First Years Massaging Action Teether',
     'rating': 2.0,
     'review': 'I had this very teether for my twin boys 8 years ago and they absolutely loved it.  So, when my new baby started teething, I sought out the same teether.  I was surprised when it arrived and the packaging stated that the product is, "safety tested" for BPA, lead, and phthalates.  It does not state ANYWHERE on the package that it is BPA free.  As a former regulator (of medical devices) I am very sensitive about company labeling and statements.  Perhaps too much so.  But, I would rather err on the side of caution where my child is concerned, and the lack of clear "BPA free" labeling on this product gives me pause.  Specifically, when they test it for BPA, lead, and phthalates, is there an acceptable amount allowed?!  If not, why wouldn\'t the company simply label the product as BPA, lead, and phthalate free?Eight years ago, when I gave this toy to my sons, no one had ever heard of BPA.  My boys put all manner of plastic toys in their mouths, and I\'m sure it was all riddled with BPA.  But, in this day and age, when BPA is strongly suspected of being dangerous, I cannot in good conscience allow my new baby to chew on anything that MAY contain it.  And, though someone on this site indicated that a representative from the company TOLD them it was BPA free, I\'m still skeptical.  Again, why not label it as such?  Most companies proudly label their products with that simple language that cannot be confused.'}




```python
def remove_punctuation(text):
    import string
    return text.translate(None, string.punctuation)

review_without_punctuation = products['review'].apply(remove_punctuation)
products['word_count'] = graphlab.text_analytics.count_words(review_without_punctuation)
```


```python
products[270]['word_count']
```




    {'8': 1L,
     'a': 2L,
     'about': 1L,
     'absolutely': 1L,
     'acceptable': 1L,
     'again': 1L,
     'age': 1L,
     'ago': 2L,
     'all': 2L,
     'allow': 1L,
     'allowed': 1L,
     'am': 1L,
     'amount': 1L,
     'an': 1L,
     'and': 10L,
     'anything': 1L,
     'anywhere': 1L,
     'arrived': 1L,
     'as': 3L,
     'baby': 2L,
     'be': 1L,
     'being': 1L,
     'boys': 2L,
     'bpa': 9L,
     'but': 2L,
     'cannot': 2L,
     'caution': 1L,
     'chew': 1L,
     'child': 1L,
     'clear': 1L,
     'companies': 1L,
     'company': 3L,
     'concerned': 1L,
     'confused': 1L,
     'conscience': 1L,
     'contain': 1L,
     'dangerous': 1L,
     'day': 1L,
     'devices': 1L,
     'does': 1L,
     'err': 1L,
     'ever': 1L,
     'for': 3L,
     'former': 1L,
     'free': 3L,
     'freeeight': 1L,
     'from': 1L,
     'gave': 1L,
     'gives': 1L,
     'good': 1L,
     'had': 2L,
     'heard': 1L,
     'i': 7L,
     'if': 1L,
     'im': 2L,
     'in': 3L,
     'indicated': 1L,
     'is': 5L,
     'it': 9L,
     'label': 3L,
     'labeling': 2L,
     'lack': 1L,
     'language': 1L,
     'lead': 3L,
     'loved': 1L,
     'manner': 1L,
     'may': 1L,
     'me': 1L,
     'medical': 1L,
     'most': 1L,
     'mouths': 1L,
     'much': 1L,
     'my': 6L,
     'new': 2L,
     'no': 1L,
     'not': 3L,
     'of': 6L,
     'on': 5L,
     'one': 1L,
     'out': 1L,
     'package': 1L,
     'packaging': 1L,
     'pause': 1L,
     'perhaps': 1L,
     'phthalate': 1L,
     'phthalates': 2L,
     'plastic': 1L,
     'product': 3L,
     'products': 1L,
     'proudly': 1L,
     'put': 1L,
     'rather': 1L,
     'regulator': 1L,
     'representative': 1L,
     'riddled': 1L,
     'safety': 1L,
     'same': 1L,
     'sensitive': 1L,
     'side': 1L,
     'simple': 1L,
     'simply': 1L,
     'site': 1L,
     'skeptical': 1L,
     'so': 2L,
     'someone': 1L,
     'sons': 1L,
     'sought': 1L,
     'specifically': 1L,
     'started': 1L,
     'state': 1L,
     'stated': 1L,
     'statements': 1L,
     'still': 1L,
     'strongly': 1L,
     'such': 1L,
     'sure': 1L,
     'surprised': 1L,
     'suspected': 1L,
     'teether': 2L,
     'teething': 1L,
     'test': 1L,
     'tested': 1L,
     'that': 6L,
     'the': 9L,
     'their': 2L,
     'them': 1L,
     'there': 1L,
     'they': 2L,
     'this': 5L,
     'though': 1L,
     'to': 2L,
     'told': 1L,
     'too': 1L,
     'toy': 1L,
     'toys': 1L,
     'twin': 1L,
     'very': 2L,
     'was': 3L,
     'when': 5L,
     'where': 1L,
     'why': 2L,
     'with': 2L,
     'would': 1L,
     'wouldnt': 1L,
     'years': 2L}




```python
products = products[products['rating']!=3]
len(products)
```




    166752




```python
products['sentiment'] = products['rating'].apply(lambda rating : +1 if rating > 3 else -1)
products
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">name</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">review</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">rating</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">word_count</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">sentiment</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Planetwise Wipe Pouch</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">it came early and was not<br>disappointed. i love ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 3L, 'love': 1L,<br>'it': 3L, 'highly': 1L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Annas Dream Full Quilt<br>with 2 Shams ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Very soft and comfortable<br>and warmer than it ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 2L, 'quilt': 1L,<br>'it': 1L, 'comfortable': ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Stop Pacifier Sucking<br>without tears with ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">This is a product well<br>worth the purchase.  I ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 3L, 'ingenious':<br>1L, 'love': 2L, 'is': ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Stop Pacifier Sucking<br>without tears with ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">All of my kids have cried<br>non-stop when I tried to ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 2L, 'all': 2L,<br>'help': 1L, 'cried': 1L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Stop Pacifier Sucking<br>without tears with ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">When the Binky Fairy came<br>to our house, we didn't ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 2L, 'cute': 1L,<br>'help': 2L, 'habit': 1L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">A Tale of Baby's Days<br>with Peter Rabbit ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Lovely book, it's bound<br>tightly so you may no ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">4.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'shop': 1L, 'be': 1L,<br>'is': 1L, 'bound': 1L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Baby Tracker&amp;reg; - Daily<br>Childcare Journal, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Perfect for new parents.<br>We were able to keep ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 2L, 'all': 1L,<br>'right': 1L, 'able': 1L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Baby Tracker&amp;reg; - Daily<br>Childcare Journal, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">A friend of mine pinned<br>this product on Pinte ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 1L, 'fantastic':<br>1L, 'help': 1L, 'give': ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Baby Tracker&amp;reg; - Daily<br>Childcare Journal, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">This has been an easy way<br>for my nanny to record ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">4.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'all': 1L, 'standarad':<br>1L, 'another': 1L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Baby Tracker&amp;reg; - Daily<br>Childcare Journal, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">I love this journal and<br>our nanny uses it ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">4.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'all': 2L, 'nannys': 1L,<br>'just': 1L, 'sleep': 2L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
</table>
[166752 rows x 5 columns]<br/>Note: Only the head of the SFrame is printed.<br/>You can use print_rows(num_rows=m, num_columns=n) to print more rows and columns.
</div>




```python
products[270]
```




    {'name': "Arm's Reach Co-Sleeper Original Bassinet, Solid Toffee",
     'rating': 4.0,
     'review': "I love the idea of the co-sleeper. I've seen some other concept designs by other companies and I hope they follow through with them. Arm's Reach has a bit of a monopoly on the co-sleepers right now. My little one hasn't arrived yet, so I haven't actually used it yet. Assembly is REALLY confusing. I don't know what happened to my paper instructions, but I can't find them. Luckily, there are some on the AR web page. But it is still so confusing.For those of us who are ardent Attachment Parenting, this is ideal. My older son, 15 months old, is still in bed with us and this Arm's Reach will give us the extra space for two little ones. We used the Snuggle Nest when our older boy was a small infant and that worked great. With two though, I wanted to keep the older away from the younger while they slept but still near us.If attachment parenting is a new concept for you, I strongly encourage you to read as much as you can online. Arm's Reach co-sleeper is a great way to co-sleep without the fear of suffocation.",
     'sentiment': 1L,
     'word_count': {'15': 1L,
      'a': 5L,
      'actually': 1L,
      'and': 3L,
      'ar': 1L,
      'ardent': 1L,
      'are': 2L,
      'arms': 3L,
      'arrived': 1L,
      'as': 2L,
      'assembly': 1L,
      'attachment': 2L,
      'away': 1L,
      'bed': 1L,
      'bit': 1L,
      'boy': 1L,
      'but': 3L,
      'by': 1L,
      'can': 1L,
      'cant': 1L,
      'companies': 1L,
      'concept': 2L,
      'confusing': 1L,
      'confusingfor': 1L,
      'cosleep': 1L,
      'cosleeper': 2L,
      'cosleepers': 1L,
      'designs': 1L,
      'dont': 1L,
      'encourage': 1L,
      'extra': 1L,
      'fear': 1L,
      'find': 1L,
      'follow': 1L,
      'for': 2L,
      'from': 1L,
      'give': 1L,
      'great': 2L,
      'happened': 1L,
      'has': 1L,
      'hasnt': 1L,
      'havent': 1L,
      'hope': 1L,
      'i': 7L,
      'idea': 1L,
      'ideal': 1L,
      'in': 1L,
      'infant': 1L,
      'instructions': 1L,
      'is': 6L,
      'it': 2L,
      'ive': 1L,
      'keep': 1L,
      'know': 1L,
      'little': 2L,
      'love': 1L,
      'luckily': 1L,
      'monopoly': 1L,
      'months': 1L,
      'much': 1L,
      'my': 3L,
      'near': 1L,
      'nest': 1L,
      'new': 1L,
      'now': 1L,
      'of': 4L,
      'old': 1L,
      'older': 3L,
      'on': 2L,
      'one': 1L,
      'ones': 1L,
      'online': 1L,
      'other': 2L,
      'our': 1L,
      'page': 1L,
      'paper': 1L,
      'parenting': 2L,
      'reach': 3L,
      'read': 1L,
      'really': 1L,
      'right': 1L,
      'seen': 1L,
      'slept': 1L,
      'small': 1L,
      'snuggle': 1L,
      'so': 2L,
      'some': 2L,
      'son': 1L,
      'space': 1L,
      'still': 3L,
      'strongly': 1L,
      'suffocation': 1L,
      'that': 1L,
      'the': 9L,
      'them': 2L,
      'there': 1L,
      'they': 2L,
      'this': 2L,
      'those': 1L,
      'though': 1L,
      'through': 1L,
      'to': 4L,
      'two': 2L,
      'us': 3L,
      'used': 2L,
      'usif': 1L,
      'wanted': 1L,
      'was': 1L,
      'way': 1L,
      'we': 1L,
      'web': 1L,
      'what': 1L,
      'when': 1L,
      'while': 1L,
      'who': 1L,
      'will': 1L,
      'with': 3L,
      'without': 1L,
      'worked': 1L,
      'yet': 2L,
      'you': 3L,
      'younger': 1L}}




```python
train_data, test_data = products.random_split(.8, seed=1)
print len(train_data)
print len(test_data)
```

    133416
    33336
    


```python
sentiment_model = graphlab.logistic_classifier.create(train_data,
                                                     target = 'sentiment',
                                                     features = ['word_count'],
                                                     validation_set = None)
```


<pre>Logistic regression:</pre>



<pre>--------------------------------------------------------</pre>



<pre>Number of examples          : 133416</pre>



<pre>Number of classes           : 2</pre>



<pre>Number of feature columns   : 1</pre>



<pre>Number of unpacked features : 121712</pre>



<pre>Number of coefficients    : 121713</pre>



<pre>Starting L-BFGS</pre>



<pre>--------------------------------------------------------</pre>



<pre>+-----------+----------+-----------+--------------+-------------------+</pre>



<pre>| Iteration | Passes   | Step size | Elapsed Time | Training-accuracy |</pre>



<pre>+-----------+----------+-----------+--------------+-------------------+</pre>



<pre>| 1         | 5        | 0.000002  | 2.463587     | 0.840754          |</pre>



<pre>| 2         | 9        | 3.000000  | 3.767649     | 0.931350          |</pre>



<pre>| 3         | 10       | 3.000000  | 4.224679     | 0.882046          |</pre>



<pre>| 4         | 11       | 3.000000  | 4.690803     | 0.954076          |</pre>



<pre>| 5         | 12       | 3.000000  | 5.134932     | 0.960964          |</pre>



<pre>| 6         | 13       | 3.000000  | 5.589740     | 0.975033          |</pre>



<pre>+-----------+----------+-----------+--------------+-------------------+</pre>



<pre>TERMINATED: Terminated due to numerical difficulties.</pre>



<pre>This model may not be ideal. To improve it, consider doing one of the following:
(a) Increasing the regularization.
(b) Standardizing the input data.
(c) Removing highly correlated features.
(d) Removing `inf` and `NaN` values in the training data.</pre>



```python
sentiment_model
```




    Class                          : LogisticClassifier
    
    Schema
    ------
    Number of coefficients         : 121713
    Number of examples             : 133416
    Number of classes              : 2
    Number of feature columns      : 1
    Number of unpacked features    : 121712
    
    Hyperparameters
    ---------------
    L1 penalty                     : 0.0
    L2 penalty                     : 0.01
    
    Training Summary
    ----------------
    Solver                         : lbfgs
    Solver iterations              : 6
    Solver status                  : TERMINATED: Terminated due to numerical difficulties.
    Training time (sec)            : 6.0401
    
    Settings
    --------
    Log-likelihood                 : inf
    
    Highest Positive Coefficients
    -----------------------------
    word_count[mobileupdate]       : 41.9847
    word_count[placeid]            : 41.7354
    word_count[labelbox]           : 41.151
    word_count[httpwwwamazoncomreviewrhgg6qp7tdnhbrefcmcrprcmtieutf8asinb00318cla0nodeid] : 40.0454
    word_count[knobskeeping]       : 36.2091
    
    Lowest Negative Coefficients
    ----------------------------
    word_count[probelm]            : -44.9283
    word_count[impulsejeep]        : -43.081
    word_count[infantsyoung]       : -39.5945
    word_count[cutereditafter]     : -35.6875
    word_count[avacado]            : -35.0542




```python
weights = sentiment_model.coefficients
weights.column_names()
```




    ['name', 'index', 'class', 'value', 'stderr']




```python
num_positive_weights = len(weights[weights['value'] >= 0])
num_negative_weights = len(weights[weights['value'] < 0])

print "Number of positive weights: %s" % num_positive_weights
print "Number of negative weights: %s" % num_negative_weights
```

    Number of positive weights: 68419
    Number of negative weights: 53294
    


```python
sample_test_data = test_data [10:13]
print sample_test_data['rating']
sample_test_data
```

    [5.0, 2.0, 1.0]
    




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">name</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">review</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">rating</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">word_count</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">sentiment</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Our Baby Girl Memory Book</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Absolutely love it and<br>all of the Scripture in ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 2L, 'all': 1L,<br>'love': 1L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Wall Decor Removable<br>Decal Sticker - Colorful ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Would not purchase again<br>or recommend. The decals ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">2.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'and': 1L, 'wall': 1L,<br>'them': 1L, 'decals': ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">-1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">New Style Trailing Cherry<br>Blossom Tree Decal ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Was so excited to get<br>this product for my baby ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1.0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">{'all': 1L, 'money': 1L,<br>'into': 1L, 'it': 3L, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">-1</td>
    </tr>
</table>
[3 rows x 5 columns]<br/>
</div>




```python
scores = sentiment_model.predict(sample_test_data, output_type='margin')
print scores
```

    [6.734619727059314, -5.7341309967603475, -14.668460404468686]
    


```python
def class_predictions(score):
    return 1 if score > 0 else -1

for score in scores:
    print 'The predicted class for {} is: {}'.format(score, class_predictions(score))
```

    The predicted class for 6.73461972706 is: 1
    The predicted class for -5.73413099676 is: -1
    The predicted class for -14.6684604045 is: -1
    


```python
print sentiment_model.predict(sample_test_data)
```

    [1L, -1L, -1L]
    


```python
import math

def class_probabilities(score):
    probability = 1 / (1 + math.exp(-score))
    return probability

for score in scores:
    print 'The probability that the score {} is class {} is: {}'.format(score, class_predictions(score), class_probabilities(score))
    
```

    The probability that the score 6.73461972706 is class 1 is: 0.998812384838
    The probability that the score -5.73413099676 is class -1 is: 0.0032232681818
    The probability that the score -14.6684604045 is class -1 is: 4.26155799665e-07
    


```python
test_data['probability'] = sentiment_model.predict(test_data, output_type='probability')
top_20 = test_data.topk('probability', 20)['name']
for item in top_20:
    print item
```

    Britax Decathlon Convertible Car Seat, Tiffany
    Ameda Purely Yours Breast Pump - Carry All
    Traveling Toddler Car Seat Travel Accessory
    Shermag Glider Rocker Combo, Pecan with Oatmeal
    Cloud b Sound Machine Soother, Sleep Sheep
    JP Lizzy Chocolate Ice Classic Tote Set
    Fisher-Price Rainforest Melodies and Lights Deluxe Gym
    Lilly Gold Sit 'n' Stroll 5 in 1 Car Seat and Stroller Combination, Tuxedo Black (sunshade is not included in the offering)
    Fisher-Price Deluxe Jumperoo
    North States Supergate Pressure Mount Clear Choice Wood Gate
    Munchkin Mozart Magic Cube
    Britax Marathon Convertible Car Seat, Granite
    Wizard Convertible Car Seat with LATCH in Midnight Print
    Capri Stroller - Red Tech
    Peg Perego Primo Viaggio Car Seat / Infant Carrier with LATCH Base - Black Sable
    HALO SleepSack Micro-Fleece Wearable Blanket, Soft Pink, Small
    Leachco Snoogle Total Body Pillow
    Summer Infant Complete Nursery Care Kit
    Safety 1st Tot-Lok Four Lock Assembly
    BABYBJORN Potty Chair - Red
    


```python
top_20 = test_data.topk('probability', 20, reverse= True)['name']
for item in top_20:
    print item
```

    Jolly Jumper Arctic Sneak A Peek Infant Car Seat Cover Black
    Levana Safe N'See Digital Video Baby Monitor with Talk-to-Baby Intercom and Lullaby Control (LV-TW501)
    Snuza Portable Baby Movement Monitor
    Fisher-Price Ocean Wonders Aquarium Bouncer
    VTech Communications Safe &amp; Sounds Full Color Video and Audio Monitor
    Safety 1st High-Def Digital Monitor
    Chicco Cortina KeyFit 30 Travel System in Adventure
    Prince Lionheart Warmies Wipes Warmer
    Valco Baby Tri-mode Twin Stroller EX- Hot Chocolate
    Adiri BPA Free Natural Nurser Ultimate Bottle Stage 1 White, Slow Flow (0-3 months)
    Munchkin Nursery Projector and Sound System, White
    The First Years True Choice P400 Premium Digital Monitor, 2 Parent Unit
    Nuby Natural Touch Silicone Travel Infa Feeder, Colors May Vary, 3 Ounce
    Peg-Perego Tatamia High Chair, White Latte
    Fisher-Price Royal Potty
    Safety 1st Exchangeable Tip 3 in 1 Thermometer
    Safety 1st Lift Lock and Swing Gate
    Evenflo Take Me Too Premiere Tandem Stroller - Castlebay
    Cloth Diaper Sprayer--styles may vary
    The First Years 3 Pack Breastflow Bottle, 9 Ounce
    


```python
def get_classification_accuracy(model, data, true_labels):
    predictions = model.predict(data)
    
    num_correct = len(predictions[predictions == true_labels])
    accuracy = num_correct / float(len(predictions))
    return accuracy

accuracy = get_classification_accuracy(sentiment_model, test_data, test_data['sentiment'])
```


```python
print 'The accuracy of the sentiment model on the test data is: {:.2f}' .format(accuracy)
```

    The accuracy of the sentiment model on the test data is: 0.91
    


```python
significant_words = ['love', 'great', 'easy', 'old', 'little', 'perfect', 'loves', 
      'well', 'able', 'car', 'broke', 'less', 'even', 'waste', 'disappointed', 
      'work', 'product', 'money', 'would', 'return']
```


```python
len(significant_words)
```




    20




```python
train_data['word_count_subset'] = train_data['word_count'].dict_trim_by_keys(significant_words, exclude= False)
test_data['word_count_subset'] = test_data['word_count'].dict_trim_by_keys(significant_words, exclude= False)
```


```python
train_data[0]['review']
```




    'it came early and was not disappointed. i love planet wise bags and now my wipe holder. it keps my osocozy wipes moist and does not leak. highly recommend it.'




```python
print train_data[0]['word_count_subset']
```

    {'love': 1L, 'disappointed': 1L}
    


```python
simple_model = graphlab.logistic_classifier.create(train_data,
                                                  target= 'sentiment',
                                                  features=['word_count_subset'],
                                                  validation_set= None)
simple_model
```


<pre>Logistic regression:</pre>



<pre>--------------------------------------------------------</pre>



<pre>Number of examples          : 133416</pre>



<pre>Number of classes           : 2</pre>



<pre>Number of feature columns   : 1</pre>



<pre>Number of unpacked features : 20</pre>



<pre>Number of coefficients    : 21</pre>



<pre>Starting Newton Method</pre>



<pre>--------------------------------------------------------</pre>



<pre>+-----------+----------+--------------+-------------------+</pre>



<pre>| Iteration | Passes   | Elapsed Time | Training-accuracy |</pre>



<pre>+-----------+----------+--------------+-------------------+</pre>



<pre>| 1         | 2        | 0.164586     | 0.862917          |</pre>



<pre>| 2         | 3        | 0.261152     | 0.865713          |</pre>



<pre>| 3         | 4        | 0.364551     | 0.866478          |</pre>



<pre>| 4         | 5        | 0.459714     | 0.866748          |</pre>



<pre>| 5         | 6        | 0.563153     | 0.866815          |</pre>



<pre>| 6         | 7        | 0.659676     | 0.866815          |</pre>



<pre>+-----------+----------+--------------+-------------------+</pre>



<pre>SUCCESS: Optimal solution found.</pre>



<pre></pre>





    Class                          : LogisticClassifier
    
    Schema
    ------
    Number of coefficients         : 21
    Number of examples             : 133416
    Number of classes              : 2
    Number of feature columns      : 1
    Number of unpacked features    : 20
    
    Hyperparameters
    ---------------
    L1 penalty                     : 0.0
    L2 penalty                     : 0.01
    
    Training Summary
    ----------------
    Solver                         : newton
    Solver iterations              : 6
    Solver status                  : SUCCESS: Optimal solution found.
    Training time (sec)            : 0.6895
    
    Settings
    --------
    Log-likelihood                 : 44323.7254
    
    Highest Positive Coefficients
    -----------------------------
    word_count_subset[loves]       : 1.6773
    word_count_subset[perfect]     : 1.5145
    word_count_subset[love]        : 1.3654
    (intercept)                    : 1.2995
    word_count_subset[easy]        : 1.1937
    
    Lowest Negative Coefficients
    ----------------------------
    word_count_subset[disappointed] : -2.3551
    word_count_subset[return]      : -2.1173
    word_count_subset[waste]       : -2.0428
    word_count_subset[broke]       : -1.658
    word_count_subset[money]       : -0.8979




```python
get_classification_accuracy(simple_model, test_data, test_data['sentiment'])
```




    0.8693004559635229




```python
simple_model.coefficients
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">name</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">index</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">class</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">value</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">stderr</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">(intercept)</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">None</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1.2995449552</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.0120888541331</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">disappointed</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">-2.35509250061</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.0504149888557</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">love</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1.36543549368</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.0303546295109</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">well</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.504256746398</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.021381300631</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">product</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">-0.320555492996</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.0154311321362</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">loves</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1.67727145556</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.0482328275384</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">little</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.520628636025</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.0214691475665</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">work</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">-0.621700012425</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.0230330597946</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">easy</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1.19366189833</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.029288869202</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">word_count_subset</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">great</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.94469126948</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0.0209509926591</td>
    </tr>
</table>
[21 rows x 5 columns]<br/>Note: Only the head of the SFrame is printed.<br/>You can use print_rows(num_rows=m, num_columns=n) to print more rows and columns.
</div>




```python
simple_model.coefficients.sort('value', ascending = False).print_rows(num_rows=21)
```

    +-------------------+--------------+-------+-----------------+-----------------+
    |        name       |    index     | class |      value      |      stderr     |
    +-------------------+--------------+-------+-----------------+-----------------+
    | word_count_subset |    loves     |   1   |  1.67727145556  | 0.0482328275384 |
    | word_count_subset |   perfect    |   1   |  1.51448626703  |  0.049861952294 |
    | word_count_subset |     love     |   1   |  1.36543549368  | 0.0303546295109 |
    |    (intercept)    |     None     |   1   |   1.2995449552  | 0.0120888541331 |
    | word_count_subset |     easy     |   1   |  1.19366189833  |  0.029288869202 |
    | word_count_subset |    great     |   1   |  0.94469126948  | 0.0209509926591 |
    | word_count_subset |    little    |   1   |  0.520628636025 | 0.0214691475665 |
    | word_count_subset |     well     |   1   |  0.504256746398 |  0.021381300631 |
    | word_count_subset |     able     |   1   |  0.191438302295 | 0.0337581955697 |
    | word_count_subset |     old      |   1   | 0.0853961886678 | 0.0200863423025 |
    | word_count_subset |     car      |   1   |  0.058834990068 | 0.0168291532091 |
    | word_count_subset |     less     |   1   | -0.209709815216 |  0.040505735954 |
    | word_count_subset |   product    |   1   | -0.320555492996 | 0.0154311321362 |
    | word_count_subset |    would     |   1   | -0.362308947711 | 0.0127544751985 |
    | word_count_subset |     even     |   1   |  -0.51173855127 | 0.0199612760261 |
    | word_count_subset |     work     |   1   | -0.621700012425 | 0.0230330597946 |
    | word_count_subset |    money     |   1   | -0.897884155776 | 0.0339936732836 |
    | word_count_subset |    broke     |   1   |  -1.65796447838 | 0.0580878907166 |
    | word_count_subset |    waste     |   1   |   -2.042773611  | 0.0644702932444 |
    | word_count_subset |    return    |   1   |  -2.11729659718 | 0.0578650807241 |
    | word_count_subset | disappointed |   1   |  -2.35509250061 | 0.0504149888557 |
    +-------------------+--------------+-------+-----------------+-----------------+
    [21 rows x 5 columns]
    
    


```python
positive_significant_words = simple_model.coefficients[simple_model.coefficients['value'] > 0]['index']
for word in positive_significant_words:
    print sentiment_model.coefficients[sentiment_model.coefficients['index'] == word]
```

    +-------------+-------+-------+---------------+--------+
    |     name    | index | class |     value     | stderr |
    +-------------+-------+-------+---------------+--------+
    | (intercept) |  None |   1   | 1.30337080544 |  None  |
    +-------------+-------+-------+---------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+-------+-------+---------------+--------+
    |    name    | index | class |     value     | stderr |
    +------------+-------+-------+---------------+--------+
    | word_count |  love |   1   | 1.43301685439 |  None  |
    +------------+-------+-------+---------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+-------+-------+----------------+--------+
    |    name    | index | class |     value      | stderr |
    +------------+-------+-------+----------------+--------+
    | word_count |  well |   1   | 0.627964877567 |  None  |
    +------------+-------+-------+----------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+-------+-------+--------------+--------+
    |    name    | index | class |    value     | stderr |
    +------------+-------+-------+--------------+--------+
    | word_count | loves |   1   | 1.5664851757 |  None  |
    +------------+-------+-------+--------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+--------+-------+----------------+--------+
    |    name    | index  | class |     value      | stderr |
    +------------+--------+-------+----------------+--------+
    | word_count | little |   1   | 0.674162457499 |  None  |
    +------------+--------+-------+----------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+-------+-------+---------------+--------+
    |    name    | index | class |     value     | stderr |
    +------------+-------+-------+---------------+--------+
    | word_count |  easy |   1   | 1.21346937822 |  None  |
    +------------+-------+-------+---------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+-------+-------+---------------+--------+
    |    name    | index | class |     value     | stderr |
    +------------+-------+-------+---------------+--------+
    | word_count | great |   1   | 1.31459245039 |  None  |
    +------------+-------+-------+---------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+-------+-------+----------------+--------+
    |    name    | index | class |     value      | stderr |
    +------------+-------+-------+----------------+--------+
    | word_count |  able |   1   | 0.174331272552 |  None  |
    +------------+-------+-------+----------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+---------+-------+---------------+--------+
    |    name    |  index  | class |     value     | stderr |
    +------------+---------+-------+---------------+--------+
    | word_count | perfect |   1   | 1.75190114392 |  None  |
    +------------+---------+-------+---------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+-------+-------+-----------------+--------+
    |    name    | index | class |      value      | stderr |
    +------------+-------+-------+-----------------+--------+
    | word_count |  old  |   1   | 0.0091223011367 |  None  |
    +------------+-------+-------+-----------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    +------------+-------+-------+----------------+--------+
    |    name    | index | class |     value      | stderr |
    +------------+-------+-------+----------------+--------+
    | word_count |  car  |   1   | 0.195263670618 |  None  |
    +------------+-------+-------+----------------+--------+
    [? rows x 5 columns]
    Note: Only the head of the SFrame is printed. This SFrame is lazily evaluated.
    You can use sf.materialize() to force materialization.
    


```python
accuracy = get_classification_accuracy(sentiment_model, train_data, train_data['sentiment'])
print 'The accuracy of the sentiment model on the train data is: {:.2f}' .format(accuracy)
```

    The accuracy of the sentiment model on the train data is: 0.98
    


```python

```
