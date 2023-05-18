# Write-a-python-program-to-find-the-longest-words.
def find_longest_words(file_path):
    longest_words = []
    max_length = 0
    try:
        with open(file_path, 'r') as file:
            for line in file:
                words = line.split()
                for word in words:
                    word_length = len(word)
                    if word_length > max_length:
                        max_length = word_length
                        longest_words = [word]
                    elif word_length == max_length:
                        longest_words.append(word)
    except FileNotFoundError:
        print("File not found.")
    except IOError:
        print("An error occurred while reading the file.")
    return longest_words

# Example usage
file_path = 'path/to/your/text/file.txt'  # Replace with the actual file path
longest_words_list = find_longest_words(file_path)
print("Longest words in the file:")
for word in longest_words_list:
    print(word)
