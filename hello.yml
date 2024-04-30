name: Build C Program 2

on: [push]

jobs:
  build:
    name: Build Hello World
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2
      
    - name: Install build tools
      run: sudo apt-get install -y mingw-w64
      
    - name: Compile C program for Windows
      run: |
        x86_64-w64-mingw32-gcc hello.c -o hello.exe
        ls -lh  # List file details for debugging
      
    - name: Commit changes
      run: |
        git config --local user.email "action@github.com"
        git config --local user.name "GitHub Action"
        git add hello.exe
        git commit -m "Add compiled executable"
      
    - name: Push changes
      uses: ad-m/github-push-action@master
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
