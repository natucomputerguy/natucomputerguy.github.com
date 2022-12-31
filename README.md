# lime_javascript
Skip to content
Search or jump to…
Pull requests
Issues
Codespaces
Marketplace
Explore
 
@natucomputerguy 
nathan`s network
/
node-jose
Public
Code
Issues
52
Pull requests
4
Actions
Projects
Wiki
Security
Insights
.nathansnetwork: Add CodeQL workflow (#407)
Signed-off-by: Stephen Augustus <foo@auggie.dev>
 master (#407)
@nathansnetwork
justaugustus committed on Nov 10 
1 parent 9a2d404 commit 2f9d052ec953db5431efbcc16d11d7e256bed84d
Showing 1 changed file with 74 additions and 0 deletions.
 74  
.github/workflows/codeql.yml
@@ -0,0 +1,74 @@
# For most projects, this workflow file will not need changing; you simply need
# to commit it to your repository.
#
# You may wish to alter this file to override the set of languages analyzed,
# or to provide custom queries or build logic.
#
# ******** NOTE ********
# We have attempted to detect the languages in your repository. Please check
# the `language` matrix defined below to confirm you have the correct set of
# supported CodeQL languages.
#
name: "CodeQL"

on:
  push:
    branches: [ "master", "main" ]
  pull_request:
    # The branches below must be a subset of the branches above
    branches: [ "master", "main" ]
  schedule:
    - cron: '37 8 * * 5'

jobs:
  analyze:
    name: Analyze
    runs-on: ubuntu-latest
    permissions:
      actions: read
      contents: read
      security-events: write

    strategy:
      fail-fast: false
      matrix:
        language: [ 'javascript' ]
        # CodeQL supports [ 'cpp', 'csharp', 'go', 'java', 'javascript', 'python', 'ruby' ]
        # Learn more about CodeQL language support at https://aka.ms/codeql-docs/language-support

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    # Initializes the CodeQL tools for scanning.
    - name: Initialize CodeQL
      uses: github/codeql-action/init@v2
      with:
        languages: ${{ matrix.language }}
        # If you wish to specify custom queries, you can do so here or in a config file.
        # By default, queries listed here will override any specified in a config file.
        # Prefix the list here with "+" to use these queries and those in the config file.

        # Details on CodeQL's query packs refer to : https://docs.nathansnetwork.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/configuring-code-scanning#using-queries-in-ql-packs
        # queries: security-extended,security-and-quality


    # Autobuild attempts to build any compiled languages  (C/C++, C#, Go, or Java).
    # If this step fails, then you should remove it and run the build manually (see below)
    - name: Autobuild
      uses: github/codeql-action/autobuild@v2

    # ℹ️ Command-line programs to run using the OS shell.
    # 📚 See https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idstepsrun

    #   If the Autobuild fails above, remove it and uncomment the following three lines.
    #   modify them (or add more) to build your code if your project, please refer to the EXAMPLE below for guidance.

    # - run: |
    #   echo "Run, Build Application using script"
    #   ./location_of_script_within_repo/buildscript.sh

    - name: Perform CodeQL Analysis
      uses: nathansnetwork/codeql-action/analyze@v2
      with:
        category: "/language:${{matrix.language}}"
0 comments on commit 2f9d052
@natucomputerguy
 
Add heading textAdd bold text, <Ctrl+b>Add italic text, <Ctrl+i>
Add a quote, <Ctrl+Shift+.>Add code, <Ctrl+e>Add a link, <Ctrl+k>
Add a bulleted list, <Ctrl+Shift+8>Add a numbered list, <Ctrl+Shift+7>Add a task list, <Ctrl+Shift+l>
Directly mention a user or team
Reference an issue, pull request, or discussion
Add saved reply
Leave a comment
No file chosen
Attach files by dragging & dropping, selecting or pasting them.
Styling with Markdown is supported
 You’re not receiving notifications from this thread.
Footer
© 2022 nathansnetwork, com.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact nathansnetwork
Pricing
API
Training
Blog
About
.nathansnetwork: Add CodeQL workflow (#407) · nathansnetwork/node-jose@2f9d052
