[greek_analysis.ipynb](https://github.com/user-attachments/files/27569954/greek_analysis.ipynb)
# Greek-social-media-analysis
Linguistic analysis{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "code",
      "execution_count": 1,
      "metadata": {
        "id": "XS6KdPQvXOKG"
      },
      "outputs": [],
      "source": [
        "texts = [\n",
        "    \"Σήμερα είχε απίστευτη ζέστη 😭\",\n",
        "    \"Δεν αντέχεται άλλο αυτή η κίνηση\",\n",
        "    \"Το φαγητό ήταν τέλειο!!!\",\n",
        "    \"Χαχαχα πεθαίνω 😂\",\n",
        "    \"Τι μέρα κι αυτή...\",\n",
        "    \"Αυτό το τραγούδι είναι φοβερό 😍\",\n",
        "    \"Δεν μπορώ άλλο με τη δουλειά 😅\",\n",
        "    \"Πάμε διακοπές επιτέλους\",\n",
        "    \"Τρελή κούραση σήμερα\",\n",
        "    \"Χαχα αυτό ήταν απίστευτο 😂\"\n",
        "]"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "all_text = \" \".join(texts)\n",
        "\n",
        "print(all_text)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "YzQMf4JlXtXz",
        "outputId": "17fe7324-d68f-42da-987d-dc571fb7a47a"
      },
      "execution_count": 2,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Σήμερα είχε απίστευτη ζέστη 😭 Δεν αντέχεται άλλο αυτή η κίνηση Το φαγητό ήταν τέλειο!!! Χαχαχα πεθαίνω 😂 Τι μέρα κι αυτή... Αυτό το τραγούδι είναι φοβερό 😍 Δεν μπορώ άλλο με τη δουλειά 😅 Πάμε διακοπές επιτέλους Τρελή κούραση σήμερα Χαχα αυτό ήταν απίστευτο 😂\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "words = all_text.split()\n",
        "\n",
        "print(words)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "UoDmrVi6X0gq",
        "outputId": "37b56feb-c521-4ae5-f602-9b9811d2bced"
      },
      "execution_count": 3,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "['Σήμερα', 'είχε', 'απίστευτη', 'ζέστη', '😭', 'Δεν', 'αντέχεται', 'άλλο', 'αυτή', 'η', 'κίνηση', 'Το', 'φαγητό', 'ήταν', 'τέλειο!!!', 'Χαχαχα', 'πεθαίνω', '😂', 'Τι', 'μέρα', 'κι', 'αυτή...', 'Αυτό', 'το', 'τραγούδι', 'είναι', 'φοβερό', '😍', 'Δεν', 'μπορώ', 'άλλο', 'με', 'τη', 'δουλειά', '😅', 'Πάμε', 'διακοπές', 'επιτέλους', 'Τρελή', 'κούραση', 'σήμερα', 'Χαχα', 'αυτό', 'ήταν', 'απίστευτο', '😂']\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "from collections import Counter\n",
        "\n",
        "word_freq = Counter(words)\n",
        "\n",
        "print(word_freq)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "GugVmngQYD5_",
        "outputId": "3015e325-587e-4ff7-a862-9d33807eda42"
      },
      "execution_count": 4,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Counter({'Δεν': 2, 'άλλο': 2, 'ήταν': 2, '😂': 2, 'Σήμερα': 1, 'είχε': 1, 'απίστευτη': 1, 'ζέστη': 1, '😭': 1, 'αντέχεται': 1, 'αυτή': 1, 'η': 1, 'κίνηση': 1, 'Το': 1, 'φαγητό': 1, 'τέλειο!!!': 1, 'Χαχαχα': 1, 'πεθαίνω': 1, 'Τι': 1, 'μέρα': 1, 'κι': 1, 'αυτή...': 1, 'Αυτό': 1, 'το': 1, 'τραγούδι': 1, 'είναι': 1, 'φοβερό': 1, '😍': 1, 'μπορώ': 1, 'με': 1, 'τη': 1, 'δουλειά': 1, '😅': 1, 'Πάμε': 1, 'διακοπές': 1, 'επιτέλους': 1, 'Τρελή': 1, 'κούραση': 1, 'σήμερα': 1, 'Χαχα': 1, 'αυτό': 1, 'απίστευτο': 1})\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "emojis = []\n",
        "\n",
        "for word in words:\n",
        "    for char in word:\n",
        "        if char in \"😂😭😍😅\":\n",
        "            emojis.append(char)\n",
        "\n",
        "print(emojis)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "vUrEnbbtYQa_",
        "outputId": "bd993618-b59a-4837-8f6e-5da23c359fe0"
      },
      "execution_count": 5,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "['😭', '😂', '😍', '😅', '😂']\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "emoji_freq = Counter(emojis)\n",
        "\n",
        "print(emoji_freq)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "zrxRT4JIYaG2",
        "outputId": "eaf67c7c-26f6-42ed-a27f-612e08b54e13"
      },
      "execution_count": 6,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Counter({'😂': 2, '😭': 1, '😍': 1, '😅': 1})\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "print(word_freq.most_common(10))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "mnvkFi9-YeeY",
        "outputId": "433b55a8-bfe6-4fcb-cefd-fb337ef89c76"
      },
      "execution_count": 7,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "[('Δεν', 2), ('άλλο', 2), ('ήταν', 2), ('😂', 2), ('Σήμερα', 1), ('είχε', 1), ('απίστευτη', 1), ('ζέστη', 1), ('😭', 1), ('αντέχεται', 1)]\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import matplotlib.pyplot as plt\n",
        "\n",
        "common_words = word_freq.most_common(5)\n",
        "\n",
        "labels = [item[0] for item in common_words]\n",
        "values = [item[1] for item in common_words]\n",
        "\n",
        "plt.bar(labels, values)\n",
        "plt.title(\"Most Frequent Words\")\n",
        "plt.xlabel(\"Words\")\n",
        "plt.ylabel(\"Frequency\")\n",
        "plt.show()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 472
        },
        "id": "fPw5VL1WYkH3",
        "outputId": "f0af8dd5-16c9-432f-a452-7b015c7b6fda"
      },
      "execution_count": 8,
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/plain": [
              "<Figure size 640x480 with 1 Axes>"
            ],
            "image/png": 
          },
          "metadata": {}
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "## Findings\n",
        "\n",
        "The dataset shows frequent emotional expression through emojis and informal vocabulary.\n",
        "\n",
        "Laughter markers such as \"χαχα\" appear repeatedly, suggesting conversational and highly informal discourse.\n",
        "\n",
        "Emojis function as pragmatic and emotional markers in online Greek communication"
      ],
      "metadata": {
        "id": "GKcm-OvQZLsM"
      }
    }
  ]
} of Greek social media language
