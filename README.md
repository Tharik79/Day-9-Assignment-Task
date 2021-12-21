# Day-9-Assignment-Task
//A)Get all the countries from Asia continent /region using Filter function
var request=new XMLHttpRequest();
request.open('GET','https://restcountries.com/v3/all');
request.send();
request.onload=function (){
    var countries=JSON.parse(this.response);
    const asia=countries.filter((country)=>{
        if(country.region==='Asia'){
            return country.name;
        }
    })
    console.log(asia);}


    //B. Get all the countries with a population of less than 2 lakhs using Filter function

    var request=new XMLHttpRequest();
    request.open('GET','https://restcountries.com/v3/all');
    request.send();
    request.onload=function (){
    var countries=JSON.parse(this.response);
    const population=countries.filter((populate)=>{
       return populate.population < 200000;
    })
    console.log(population);}


  // C)  Print the following details name, capital, flag using forEach function

        var request=new XMLHttpRequest();
        request.open('GET','https://restcountries.com/v3/all');
        request.send();
        request.onload=function (){
        var countries=JSON.parse(this.response);

         countries.forEach((e) => { console.log(e.name, e.capital, e.flags); 
        })
         }


    // D) Print the total population of countries using reduce function

         var request=new XMLHttpRequest();
        request.open('GET','https://restcountries.com/v3/all');
        request.send();
        request.onload=function (){
        var countries=JSON.parse(this.response);

        const population=countries.reduce((total, num)=>{
            return total+num.population;
        })
        console.log(population);}


    // E) Print the country which uses US Dollars as currency.
    
        var request=new XMLHttpRequest();
        request.open('GET','https://restcountries.com/v3/all');
        request.send();
        request.onload = function () {
            var countries = JSON.parse(this.response);
            const currency=countries.filter((country)=>{
                        if(country.currencies[0]==='United States dollars'){
                            return country.name;
                        }
                    })
                    console.log(currency);
                            
             }
            
