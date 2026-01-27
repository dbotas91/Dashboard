---
dg-publish: true
---

# Programas simples

|   |   |
|---|---|
|![](Dashboard/Attachments/clock_gray%2052.svg)Created|@August 21, 2021 6:08 PM|
|![](Dashboard/Attachments/list_gray%20764.svg)Tags||

```JavaScript
var n;
function menu(){
do{
var n = prompt("
Mini Games:
Guess the number (1)
Rock, Paper, Scissors (2)
Wordle (3)
Connect Four (4)
Tic Tac Toe (5)
Select a game (press a number or 'q' do quit: ");
if(n < 1 || n > 5 || n !== 'q' || n !== 'Q'){
console.log("O valor inserido é inválido!")
}else if(n == 1){
guessTheNumber0To10();
}else if(n == 2){
rockPaperScissors();
}else if(n == 3){
wordle();
}else if (n == 4){
ConnectFour();
}else if(n == 5){
ticTacToe();
}else{
console.log("Quitting...");
break;
}
}while(n != 'q' || n != 'Q');
}
```

```JavaScript
function guessTheNumber0To10(){
//https://www.codegrepper.com/code-examples/javascript/javascript+random+number+between+0+and+3
var n = Math.floor(Math.random() * 10),
d, num_guesses=0;
do{
	d = prompt("Insira um número");
	num_guesses++;
	if(n < d){
		alert("O número inserido é maior do que o gerado");
		}
	else if(n > d){
		alert("O número inserido é menor do que o gerado");
		}
	else{
		alert("O número é igual: " + n);
		alert("Número de tentativas: " + num_guesses);
	}
}while(n != d);
}
```

```JavaScript
function rockPaperScissors(){
var r="rock",p="paper",s="scissors",
all_choices = [r,p,s];
do{
  var n = Math.floor(Math.random() * 2),
	d = prompt("Pedra, papel, tesoura... \nEscolha 1=rock,2=paper,3=scissors, q=quit");
	let user_choice = all_choices[d-1],	computer_choice = all_choices[n];
  if(d=='q' || d=='Q'){alert("Sair do jogo"); break;
    }
  if(user_choice == computer_choice){
		alert("Empate \n"+"User chose "+user_choice+", computer chose "+computer_choice);
		}
	else if((user_choice == r && computer_choice == s) || (user_choice == p && computer_choice == r) || (user_choice == s && computer_choice == p)){
		alert("Ganhou \n"+"User chose "+user_choice+", computer chose "+computer_choice);
		}else{
		alert("Perdeu \n"+"User chose "+user_choice+", computer chose "+computer_choice);
	}
}while(d != 'q' || d!='Q');
}
```

```JavaScript
//npm install random-words
//npm install random-word-by-length
//Use node.js
function wordle(){
//var randomWords = require('random-words');
	var randomWord = require('random-word-by-length');
	let word = randomWord(5);
	let num_guesses=0,
	guessDict = {
		0: " ".repeat(5),
		1: " ",
		2: " ",
		3: " ",
		4: " ",
		5: " "
		};

	function drawBoard(){
		let txt = "";
		for(let guess in guessDict){
			txt+= " | " + guess_dict[guess]);
		}
		console.log("=======================");
	}

	function play(){
		while(true){
			drawBoard();
			let user_guess = prompt("Advinhe a letra");
		}
	}
}

//var randomWord = require('random-word-by-length');
let word = "guess"//randomWord(5);
let num_guesses=0;
let guessDict = {0:" ".repeat(5), 1:" ".repeat(5), 2:" ".repeat(5), 3:" ".repeat(5), 4:" ".repeat(5), 5:" ".repeat(5)};
let txt ="";
let txt1 ="";
function drawBoard(){
    //for(let word in guessDict){
	for(let x in Object.values(guessDict)){
		txt += " | " + x.values();
	}
        txt1=txt;
    console.log(txt1);
    console.log("=============================");
    //}
}


function initBoard(){
	let board=[];
	let row=[];
	let letter = ' _ ';
	for(let i =0; i<6;i++){
		board[i] = row;
		for(let j=0;j<5;j++){
		  if(j == 0){
	      board[i][j] = '|'+letter+'|';
      }else{
        board[i][j] = letter+'|';
      }
		}
	}
	console.log(board);
// É possível fazer semelhante com 1 linha:
// const arr2d = [...Array(6)].map(() => Array(5).fill(" _ "))
// console.log(arr2d);
}
```