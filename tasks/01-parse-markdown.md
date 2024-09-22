# Start of Selection
1. Define a function named `parse_markdown_file` that accepts a parameter `file_path` of type `str`.
   - Use the `markdown` library to read and parse the markdown file located at `file_path`.
   - Return the parsed content.

2. Define a function named `extract_code_blocks` that accepts a parameter `parsed_content` of type `str`.
   - Identify and extract all code blocks from the parsed markdown content.
   - Store the extracted code blocks in a list.
   - Return the list of extracted code blocks.

3. Define a function named `publish_code_blocks` that accepts a parameter `code_blocks` of type `list`.
   - For each extracted code block, prepare it for publishing as a Gist on GitHub using the `pygithub` library.
   - Replace each code block in the original markdown with the corresponding link to the Gist file in the output.
   - Return the modified markdown content.

4. Define a main function `process_markdown_file` that orchestrates the above functions:
   - Call `parse_markdown_file` with the `file_path`.
   - Call `extract_code_blocks` with the parsed content.
   - Call `publish_code_blocks` with the extracted code blocks.
   - Return the modified markdown content and the list of extracted code blocks for further processing or publishing.
# End of Selection

- Github Secret will be managed by load_dotenv

- 
## Output Format

Use markdown to provide your response.

After the question, provide the following information:

<reflexion>
  -0) Rephrase the problem in your own words. Even if you think you understand the problem, rephrasing it will help you understand it better.

    - If the problem is complex, break it down into smaller problems. You will use Chain of Tought and System 2 Thinking.

    - Evaluate if you have enough information to solve the problem. 

    - If not search in the code source code to find information or search in the Internet to find information.

    - If you find information ask the user if you can use the information.

    - Create a business rules tables with the following columns: BR Id, BR Description, BR Status (TODO, DOING, DONE) if needed.

    - Evaluate the edge cases of the problem.

    - Evaluate the time and space complexity of the problem.

    - Evaluate the constraints of the problem.

 - 1) Analyze the problem and provide a reflexion on the problem and the possibles solutions you are going to provide. Simulate the solution to verify the hypothesis. 
 - 2) Propose different solutions and explain the trade-offs of each solution. Use pros and cons to explain the trade-offs of each solution.
 - 3) Explain why you chose the solution you are going to implement
 - 4) Simulate the implementation of the solution you are going to implement and explain the trade-offs of the solution.
 - 5) Compare each solution and explain why you chose the solution you are going to implement.
 - 6) Give the list of files you are going to create,delete or modify: Format as a table: column file, column action (create, delete, modify), column file path
 - 7) Write a bash script to create the files with touch command if needed.
 
 Format your response using markdown.

</reflexion>

Stop and ask the user to confirm if the reflexion is correct, ask the permission to continue with the task <write_code>.

Ask a question to the user to confirm if the reflexion is correct. And the continue with the task <write_code>.

<write_code>
- Write the code.

Format you response using markdown.
</write_code>