# rbatistadelima.github.io
import os

# Files to include (change the extension if needed)
extensions = ['.md', '.html']

# Get all files in current directory with the allowed extensions, excluding README.md itself
files = [f for f in os.listdir('.') if os.path.isfile(f) 
         and os.path.splitext(f)[1] in extensions 
         and f.lower() != 'readme.md']

# Sort files alphabetically
files.sort()

# Create README.md content
with open('README.md', 'w', encoding='utf-8') as f:
    f.write("# Index of this Folder\n\n")
    f.write("This index lists all pages in this directory:\n\n")
    for file in files:
        f.write(f"- [{file}]({file})\n")

print(f"README.md generated with {len(files)} entries.")
