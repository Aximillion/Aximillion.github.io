Hey here is my code and it works as intended!

I followed the teams video guide till I got the image slider to work after that I managed to figure out most of it on my own. I aksed chatGPT for some help for example:
my slider wasnt working and the 1 small issue that caused it was "};" was right after the first line of function. so everything was outside function.

I had an older code which also worked but it had issues with "back" button. and I couldnt get images to work so I had ImageUrl inside an array. I can provide old code below:

old code:

// JAG TOG HJÄLP AV CHATGPT. gjorde egen kod och fick den att funka att den gick fram men fastnade sen när man gick back. fick inte bild att funka och därför har jag länkar.

// Jag tittade också på teams video från sista lektion för att följa lite gran för att ändra slides. 


imageCounter = 0;

let animal = [{
        animalHeader: "Horse",
        description: "This is a horse.",
        imageUrl: "https://preview.redd.it/a604rad7j4651.png?auto=webp&s=63112b65e516d3e19dcbd05489d09967a2d73dce"
    },
    {
        animalHeader: "dog",
        description: "This is a dog.",
        imageUrl: "https://www.boredpanda.com/blog/wp-content/uploads/2023/04/644a230e3f5d4_l7ink8py2vta1__700.jpg"
    },
    {
        animalHeader: "wolf",
        description: "This is a wolf.",
        imageUrl: "https://insidethemagic.net/wp-content/uploads/2017/03/Bigbadpractical.jpg"
    }
];

// changes name, description and image. 

function updateSlide(){
    const currentAnimal = animal[imageCounter];
    document.getElementById("slide-heading").innerHTML = currentAnimal.animalHeader;
    document.getElementById("slide-text").innerHTML = currentAnimal.description;
    document.getElementById("slide-img").src = currentAnimal.imageUrl;
    document.getElementById("slide-nr").innerHTML = `${imageCounter +1 }/ ${animal.length}`;
}

// makes it go back button pretty straight forward and next goes next


function goBack(){
    imageCounter--;
    if(imageCounter<= 0){
        imageCounter = animal.length;
    }
    updateSlide();
}

function goNext(){
    imageCounter++;
    if(imageCounter>= animal.length){
        imageCounter = 0;
    }
    updateSlide();
}

// declared updateslide to make code run.


