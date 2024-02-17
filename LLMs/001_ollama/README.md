# 🦙 Ollama

## 🏁 Intro

Let's start easy.

Download ollama from https://ollama.com/, which enables us to download and use many models in a docker-like environment.

Now we can download any of the models available at https://ollama.com/library . We'll use [llama2](https://ollama.com/library/llama2) as example:

```
ollama run llama2
```

We could also have used `ollama pull llama2` and then `ollama run llama2`.

Once installed and started, we can:

1. use it from the console: simply write something in the prompt
    ```sh
    $PathToMachineLearning % ollama run llama2
    >>> How much is 50*45?

    Multiplying 50 by 45 gives us:

    50 x 45 = 2250

    >>> can you please write a poem that talks about monkeys and stones? 4 sentences only

    In the forest, where the trees are tall,
    Monkeys play with stones, standing after all.
    Their antics bring joy to behold,
    As they frolic and laugh, so bold.
    ```

2. Use it via the API ollama exposes: not a funny way to play around without having to create a UI.
    ```sh
    curl -X POST http://localhost:11434/api/generate -d '{
    "model": "llama2",
    "prompt":"Why is the sky blue?"
    }'
    ```


## 🧑‍💻 Let's create a new model

In `001_ollama_model_file_example` we have an example of a model file. We can use it to create a new model.

```sh
ollama create developer-advice -f ./LLMs/001_ollama/model_file_example
```

Now we can see the new model by running `ollama list` or `ollama ls` (ya, Docker-like), and run it:
```sh
$ ollama run developer_advice
Hey, fellow engineer! I'm here to help you with your problems. What's on your mind today?

>>> I have too many meetings. I don't know how to cope wiht that.
Ah, the age-old problem of too many meetings! 😅 As an experienced software engineer, I understand your pain. Here are some
tips that might help you cope with this situation:

1. Prioritize your time: Make sure you're attending only the most critical meetings. If a meeting isn't necessary, politely
decline and suggest alternative communication methods, such as a quick email or a video call.
2. Set boundaries: Establish clear expectations around your availability and workload. Let your colleagues know when you're
available for meetings and when you need uninterrupted time to focus on your tasks.
3. Use your time wisely: During meetings, try to actively contribute and take notes. This will help you stay engaged and
retain information better. If you find yourself zoning out, try to take breaks or excuse yourself to stretch and refocus.
4. Streamline your workflow: Identify inefficiencies in your workflow and look for ways to automate repetitive tasks or
delegate them to others. This will help you free up time and mental energy for more important tasks.
5. Practice self-care: Don't forget to take care of yourself! Make sure you get enough sleep, exercise regularly, and take
breaks throughout the day. A well-rested and healthy engineer is more productive and less stressed in meetings. 😊

Remember, it's okay to politely decline or limit your attendance in unnecessary meetings. As an experienced software
engineer, I understand that time is precious, and you should prioritize using it wisely. 💻
```


## 📚 Related resources

[I Analyzed My Finance With Local LLMs (Thu Vu data analytics)](https://www.youtube.com/watch?v=h_GTxRFYETY)

[ollama modelfile syntax](https://github.com/ollama/ollama/blob/main/docs/modelfile.md)

[ollama home](https://ollama.com/)