1. Regex expression that matches 3 & 4.
	```
    /.*\/(our-resources\/news|example)\/\?p=\d{3,}/g
    ```
2. CSS selector is below.
    ```
    div.innerContainer > span.paragraphBodyStyle:first-of-type > img:first-of-type {
        border: 10px dotted pink;
    }
    ```
3. Function to display result of JSON. Just call result(cart) with cart being in the format of the question.
    ```
    function result(cart) {
        console.log("Items: " + cart.Items);
      for (var item in cart.Item) {
        console.log(' - ' + item + ' (' + cart.Item[item].price + ')');
      }
      console.log('Total: ' + cart.Total)
    }
    ```
4. Bookmarklet below.
    ```
    javascript:(function()%7Bvar%20query%20%3D%20window.location.search%3Bif%20(query)%20%7Bvar%20param%20%3D%20%5B%5D%3Bvar%20result%20%3D%20%7B%7D%3Bquery%20%3D%20query.substring(1)%3Bvar%20queryArray%20%3D%20query.split(%22%26%22)%3Bfor%20(var%20i%20%3D%200%3B%20i%20%3C%20queryArray.length%3B%20i%2B%2B)%20%7Bparam%20%3D%20queryArray%5Bi%5D.split(%22%3D%22)%3Bresult%5Bparam%5B0%5D%5D%20%3D%20param%5B1%5D%3B%7Dvar%20userPrompt%20%3D%20prompt('Enter%20a%20parameter%3A')%3Bif%20(userPrompt%20in%20result)%20%7Balert('URL%20parameter%20value%3A%20'%20%2B%20result%5BuserPrompt%5D)%3B%7D%20else%20%7Balert('That%20value%20doesn%5C't%20exist')%3B%7D%7D%20else%20%7Balert(%22There%20doesn%5C't%20seem%20to%20be%20any%20parameters%20on%20this%20website%22)%3B%7D%7D)()
    ```

5. Business Rule 3 is below
    ```
    <business-rule id="1" name="Rule-1">
      <condition>
        <or>
          <when>
            <event event-type="onPageLanding"/>
          </when>
          <when>
            <event event-type="onChatIconClicked">
              <delay>
                <duration>PT5S</duration>
              </delay>
            </event>
          </when>
        </or>
        <and>
          <not>
            <url-match regexp=".*\/test\/.*"/>
          </not>
          <number-compare test="less-than-or-equal-to">
            <landing-count counter-name="ContactUs"/>
            <count>0</count>
          </number-compare>
          <number-compare test="less-than">
            <as-number>
              <js-string-ref js-var-id="cart.Total"/>
            </as-number>
            <number>100</number>
          </number-compare>
        </and>
      </condition>
    </business-rule>
    ```
