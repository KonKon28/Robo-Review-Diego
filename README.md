# GPT-2 Review Generation with N-Shot Prompting

## Project Overview

This project demonstrates how to generate customer product reviews using GPT-2 with **N-shot prompting** to guide the model towards more organic and contextually appropriate reviews. The script leverages the Hugging Face `transformers` library to fine-tune the model's output based on user input.

The model is fed a series of N-shot examples of customer reviews with varying sentiments (positive, negative, and neutral) before generating its own review based on the specified product, category, and sentiment.

## Features

- **N-shot Prompting**: Provides the model with pre-defined examples to influence its output, resulting in more coherent and contextually relevant reviews.
- **Sentiment Control**: The generated review can be tailored to a specific sentiment — `positive`, `negative`, or `neutral`.
- **Custom Product & Category**: Users can specify the product and category for which they want a review.
- **Randomized Output**: Each run produces a unique review, even with the same input, thanks to the GPT-2 model’s generative capabilities.

## Requirements

To run this project, you need the following libraries installed:

```bash
pip install transformers
```

The model is based on the Hugging Face `transformers` library and utilizes GPT-2 for text generation.

## How It Works

1. The model takes a series of **N-shot examples** (i.e., examples of product reviews for different sentiments) as input.
2. The user provides the **product name**, **category**, and desired **sentiment** (positive, negative, or neutral).
3. The script generates a natural-sounding review based on the user’s input while leveraging the given examples to guide the model’s output.
4. The final output excludes the N-shot examples from the generated review, ensuring only the newly generated text is displayed.

## Code Structure

- **Review Generation Pipeline**: The model pipeline is built using GPT-2 (`gpt2` model) from Hugging Face. It generates the review based on the constructed prompt and N-shot examples.
- **N-shot Prompting**: Before generating the review, several examples (positive, negative, and neutral reviews) are passed to the model as a reference.
- **Sentiment Selection**: The user selects a desired sentiment, and the model tailors its review output accordingly.

### Example Input and Output

1. **Input:**
   - Product: `Samsung Phone`
   - Category: `Smartphone`
   - Sentiment: `Negative`
   
2. **Generated Review:**
   ```
   I bought the Samsung Phone in the Smartphone category and it was quite disappointing. I was not happy because the phone’s battery drained quickly, and it lagged while using basic apps. The overall performance was below expectations.
   ```

## How to Use

1. Clone the repository or download the script.
2. Install the required dependencies using the command: `pip install transformers`.
3. Run the script. It will prompt you to provide:
   - **Product Name**
   - **Category**
   - **Sentiment** (Positive, Negative, Neutral)
4. The model will generate a review based on the provided inputs.

### Running the Script

```bash
python review_generation.py
```

After running the script, it will ask for the product details and the desired sentiment. Based on the inputs, it will generate a review influenced by the N-shot examples and display the result.

## Customization

You can customize the N-shot examples by modifying the `n_shot_examples` list in the script. For instance, you can add or remove examples to better suit your domain or use case.

Example for adding a new `positive` review to the list:

```python
n_shot_examples = [
    "I bought the headphones and they were absolutely amazing! The sound quality was crystal clear and the comfort was top-notch. I would highly recommend them to anyone. (Positive)",
    "I purchased the phone charger and it was disappointing. It broke within a week and didn’t work well at all. I wouldn’t recommend this to others. (Negative)",
    "I got the blender, and it was okay. It worked as expected, but there was nothing special about it. It does the job, but I don’t feel strongly either way. (Neutral)",
    "I bought the new tablet and it exceeded my expectations! The screen resolution is stunning and the performance is flawless. (Positive)"  # New example added
]
```

## License

This project is open-source and available under the MIT License.
