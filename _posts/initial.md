---
layout: post
title:  "Progress so far"
date:   2023-02-14 
categories: OSSU
---

Considering the rise of self-taught developers, which about a third of them not being officially taught in university where I am from, to the celebration of many (or dismay), the landscape has changed quite a bit, but now with the invention of AI tools, like ChatGPT and soon-to-be Bard AI from Google (if it doesn't cost them a few billion), it seems the foundations of our profession seems to be on shaky ground.

Now AI won't replace Software Developers anytime soon. OpenAI, the makers of ChatGPT have begun hiring more developers to train their supreme AI overlord to one day replace us all. This has had the anxiety inducing affect on me of realising that upskilling is even more important than it ever was, in an already competitive market, trying to compete against an AI isn't something I envisioned myself doing.

I started going through the OSSU curriculum to get a solid foundations of the principles of computer science. As a self-taught developer as well, it's easy to fall into a comfort zone, as you get to a certain level of expertise and think you are fine, and you probably will be for the most part. But the foundations are lacking and that is something I found myself needing to learn them.

> This will be the first in a series I'll dedicate to the process of going through the curriculum and my struggles and personal revelations along the way, of which I am sure will be many.

I have been busy with the OSSU curriculum for about a month or two and I have learn a lot of things I probably wouldn't have thought of on my own as it never truly occured to me.

The first ***course*** that I did was the **Introduction to Computer Science (CS50x)** by Harvard, which is great, but I found that all the interesting bits was more in the first few weeks of the course, like working with WAV files, building photo filters, and then some manual memory management concepts, which I found surprisingly fun (probably because I hate myself). Soon after the course focused on python which re-hashes the same ideas learned earlier and isn't necesarrily something new and then focuses on HTML, CSS, JavaScript and Flask for web applications, which wasn't something that interested me.

At the end of the day, would I recommend the course? **Yes...yes, I would**

On a side note, one problem set you complete is quite fun, the spell checker. (in C...so yes, there is memory management)

```c
// Implements a dictionary's functionality

#include <ctype.h>
#include <stdbool.h>
#include <stdlib.h>
#include <string.h>
#include <stdio.h>

#include "dictionary.h"

// Represents a node in a hash table
typedef struct node
{
    char word[LENGTH + 1];
    struct node *next;
}
node;

// Add a index for garbage words
const unsigned int N = (26 * 26) + 1;
unsigned int count = 0;

// Hash table
node *table[N];

void RecurseFree(node *ptr);

// Returns true if word is in dictionary, else false
bool check(const char *word)
{
    // TODO
    if (strcmp(word, " "))
    {
        int hash_index = hash(word);
        if (hash_index >= 0)
        {
            node *ptr = table[hash_index];
            if (ptr == NULL)
            {
                return true;
            } else
            {
                int compare = 0;
                char *temp_buffer = malloc(strlen(word));
                for (int i = 0; word[i] != '\0'; i++)
                {
                    temp_buffer[i] = tolower(word[i]);
                }
                while (ptr != NULL)
                {
                    compare = strcmp(ptr->word, temp_buffer);
                    ptr = ptr->next;
                    if (compare == 0)
                    {
                        free(temp_buffer);
                        return true;
                    }
                }
                free(temp_buffer);
                return false;
            }
        }
    }

    return true;
}

// Hashes word to a number
unsigned int hash(const char *word)
{
    int hash_value = (toupper(word[0]) - 'A') + (toupper(word[1]) - 'A');
    // TODO: Improve this hash function
    return hash_value < 0 ? N - 1 : hash_value;
}

// Loads dictionary into memory, returning true if successful, else false
bool load(const char *dictionary)
{
    // TODO
    FILE *chosen_dictionary = fopen(dictionary, "r");
    if (chosen_dictionary == NULL)
    {
        return false;
    }

    fseek(chosen_dictionary, 0, SEEK_END); // seek to end of file
    int size = ftell(chosen_dictionary); // get current file pointer
    fseek(chosen_dictionary, 0, SEEK_SET);

    //Holds word temporarily in memory
    char buffer[LENGTH + 1];
    for (int i = 0, buffer_i = 0; i < size; i++)
    {
        //Holds word temporaroly
        fread(&buffer[buffer_i], sizeof(char), sizeof(char), chosen_dictionary);

        if (buffer[buffer_i] == 10)
        {
            int hash_table_index = hash(buffer);
            if (table[hash_table_index] == 0)
            {
                // Adds a new node to the hash table is there isn't a value
                // Allocates memory for a word
                node *new_node = malloc(sizeof(node));
                buffer[strcspn(buffer, "\r\n")] = '\0';
                strcpy(new_node->word, buffer);
                new_node->next = NULL;
                // Adds node to the hash table
                table[hash_table_index] = new_node;
                count++;
            } else
            {
                // Gets first item
                node *head = table[hash_table_index];

                // Adds item to the front
                node *new_node = malloc(sizeof(node));
                //printf("Got Here\n");
                buffer[ strcspn(buffer, "\r\n") ] = '\0';
                strcpy(new_node->word, buffer);
                new_node->next = head;

                if (new_node->next == NULL)
                {
                    return false;
                }

                table[hash_table_index] = new_node;
                count++;
            }
            buffer_i = 0;

            // Continue to next word
            continue;
        }

        buffer_i++;
    }
    fclose(chosen_dictionary);
    return true;
}

// Returns number of words in dictionary if loaded, else 0 if not yet loaded
unsigned int size(void)
{
    return count;
}

// Unloads dictionary from memory, returning true if successful, else false
bool unload(void)
{
    for (int i = 0; i < N; i++)
    {
        RecurseFree(table[i]);
    }
    return true;
}

void RecurseFree(node *ptr)
{
    if (ptr == NULL)
    {
        return;
    }
    RecurseFree(ptr->next);
    free(ptr);
}
```

After the completion of the CS50 course I went to the next two in the OSSU Curriculum:
- How to Code: Simple data.
- How to Code: Complex Data.

Ultimately, I decided to skip these two as most of the problems and practical assignments were behind a paywall and simply provided no benefit other that watching some videos.

I moved on to the **Programming Languages part A** on Coursera, which I am still currenly busy with and will update further when I have completed the course.

------------

If you've come this far, thank you for reading, I appreciate it and I wish you all the best on your coding adventures. Till next time.
