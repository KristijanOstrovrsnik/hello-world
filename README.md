# Number guessing game
using System.Collections;
using System.Collections.Generic;
using System.Runtime.InteropServices;
using UnityEngine;

public class HelloWorld : MonoBehaviour
{
    int max;
    int min;
    int guess;

    // Start is called before the first frame update
    void Start()
    {
        StartGame();
    }

    void StartGame()
    {
        max = 1000;
        min = 1;
        guess = 500;

        Debug.Log("Welcome to number wizard, hold on to your panties!");
        Debug.Log("If you wanna play think of a number.");
        Debug.Log("The highest number you can pick is: " + max);
        Debug.Log("The lowest number you can pick is: " + min);
        Debug.Log("Tell me if your number is higher or lower than:" + guess);
        Debug.Log("Push Up = higher, Push Down = lowe, Push Enter = correct.");
        max = max + 1;
    }

    // Update is called once per frame
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.UpArrow))
        {
            Debug.Log("As you say i will guess higher.");
            min = guess;
            NextGuess();
        }
        

        else if (Input.GetKeyDown(KeyCode.DownArrow))
        {
            Debug.Log("As you say i will guess lower.");
            max = guess;
            NextGuess();

        }

        else if (Input.GetKeyDown(KeyCode.Return))
        {
            Debug.Log("Yay i've guessed correctly! You owe me a beer.");
            StartGame();
        }
    }
    
    void NextGuess()
    {
        guess = (max + min) / 2;
        Debug.Log("I guess: " + guess);
    }
}

