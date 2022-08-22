# covid19-visualization
the perpuse of this project is to learn the Chart.js library after they change the syntax so it must to go through it and learn the new syntax 
the project is just a small visualization of the COVID19 data 

if you see the `App.vue` you will find the API call 

```JS
async created(){
    const {data} = await axios.get('https://api.covid19api.com/live/country/egypt')
    data.forEach(d => {
      const date = moment(d.Date,"YYYYMMDD").format("YYYY/MM/DD")
      const {Confirmed,Deaths,Recovered} = d
      this.PositiveCases.push({date, total : Confirmed})
      this.Deaths.push({date, total : Deaths})
      this.Recoverd.push({date, total : Recovered})
      this.dates = this.PositiveCases.map(d => d.date)
      this.PositiveCasestotals = this.PositiveCases.map(d => d.total)
      this.DeathsToltals = this.Deaths.map(d => d.total)
      this.RecoverdToltals = this.Recoverd.map(d => d.total)
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

# ScreenShots

![image](https://user-images.githubusercontent.com/42722816/185997734-b57a98d5-d8ab-49c6-8f9f-47b72bcbf975.png)

![image](https://user-images.githubusercontent.com/42722816/185997791-651f1833-e62a-4074-b122-d341f25a10f1.png)

![image](https://user-images.githubusercontent.com/42722816/185998022-839ce92d-5240-40f8-b8a7-f40b63ac7084.png)

![image](https://user-images.githubusercontent.com/42722816/185998121-e85ea44a-1566-4896-bdad-870438b9cb32.png)

![image](https://user-images.githubusercontent.com/42722816/185998200-821c6754-75cc-44be-b41f-bf6ad3aeefb1.png)
