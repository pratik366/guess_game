# Guessing game
use rand::seq::SliceRandom;
use std::io;
mod guess_num;

fn main(){
    guess_num::main();
    let arr: [&str; 4]=["apple","banana","mango","santra"];
    let mut rng=rand::thread_rng();
    let computer_word = arr.choose(&mut rng).
                expect("Failed to choose a word");

    println!("Welcome to guessing game");
    if let Some(computer)=arr.choose(&mut rng){
       // println!("computer choose: {}",computer);
    }
    loop {
        println!("Guessing words are : {:?}",arr);
        println!("please guessed a word : ");
        let mut input=String::new();
        io::stdin().read_line(&mut input).expect("failed to input");
        println!("you guessed: {}",&mut input);
        let input:&str= input.trim(); // convert String to &str
        
        if input == *computer_word{ // * is used to dereference of &str 
            println!("congratulations you guessed it !!!");
            break;
        }
        else{
                println!("OOPs wrong guessed");
        }
       
    }
}
        


