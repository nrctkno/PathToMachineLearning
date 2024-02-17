# OLlama

## Intro

Let's start easy.

https://ollama.com/ download OLlama, which enables us to download and use many models in a docker-like environment.

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

2. Use it via the API OLlama exposes: not a funny interface to play around without having to create a UI.
```
curl -X POST http://localhost:11434/api/generate -d '{
  "model": "llama2",
  "prompt":"Why is the sky blue?"
 }'
```

## Related resources

[I Analyzed My Finance With Local LLMs (Thu Vu data analytics)](https://www.youtube.com/watch?v=h_GTxRFYETY)