# presented
Simple CLI for developers from starter to advanced.

```py
from presented import CLI

cli = CLI()

@cli.command(
  name="hello"
)
def greet(session):
  session.echo("Hello!")

if __name__ == "__main__":
  cli() # start the CLI
```

## Advanced
```py
import time
from presented import CLI

cli = CLI()

@cli.command(
  name="install",
  help="Install a project."
)
def installation(session):
  with session.Progress() as progress:
  
    @progress.tab(
      name="🚀 Launching Request"
    )
    def step1(status):
      status >> "Installing..."
      
      ... # your code
      
      status >> "Installation completed!"
      
    @progress.tab(
      name="✨ Wasting Your Time"
    )
    def step2(status):
      time.sleep(10)
      
  session.echo("Installation complete!")
  
if __name__ == "__main__:
  cli()
```
