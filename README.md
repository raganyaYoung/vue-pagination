# vue-pagination
A pagination component for vue
![vue pagination] (http://github.com/raganyaYoung/vue-pagination/raw/master/screenshots/1.jpg) 

## Installation
vue-pagination for using required vuejs and bulma 
[Vue.js](http://vuejs.org)
[bulma](http://bulma.io)

## Configuration
```
import Vue from 'vue'
import bulma from 'bulma'
import Pagination from 'pagination.vue'

export default {
    data() {
      return {
        current_page: 1,
        rdata_count: '',
        total_pages: '',
        pageSize: 20,
      }
    },
    components: {
        Pagination
    }
}
```

## Example
```
    <Pagination 
        :current_page.sync="current_page" 
        :total_pages.sync="totalpages" 
        :count.sync="rdata_count">
    </Pagination>
```
```
    new Vue({
      el: '#app',
      data: function () {
        return {
            current_page: 1,
            rdata_count: '',
            total_pages: '',
            pageSize: 20,
            list: [],
        }
      },
      components: {
        Pagination
      }
      watch: {
        'current_page': function() {
            this.getList()
        },
      },
      methods: {
        getList() {
            fetch(url)
              .then(res => res.json())
              .then(json_res() => {
                 Vue.set(this, 'rdata_count', json_res.count)
                 Vue.set(this, 'total_pages', Math.ceil(json_res.count/this.pageSize))
              })
        },
      },
    })
```

## Options
| Name          | Type     | Default | Required | Description     |
| ------------- |:--------:| -------:| --------:| ---------------:|
| current_page  | INTEGER  | 1       | true     | current page    |
| total_pages   | INTEGER  |         | true     | total pages     |
| count         | INTEGER  |         | true     | the count of your  |






