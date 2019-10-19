# ENV variables
Sinatra is built on a technology called Rack. Rack provides Sinatra with a built-in variable, ENV. It's available anywhere in Sinatra.

An Environment Variable is a special kind of constant: one that tells the application something about its current environment.

Store config in environment variables (often shortened to env vars or env). Env vars are easy to change between deploys without changing any code; unlike config files, there is little chance of them being checked into the code repo accidentally; and unlike custom config files, or other config mechanisms such as Java System Properties, they are a language- and OS-agnostic standard.

Every program you run on your server gets its own set of environment variables at the moment you launch it. Since environment variables belong to processes, that means whenever the process quits, your environment variable goes away.  If you want them to persist across sessions, you have to store them in some kind of configuration file like .bashrc

Every process has a parent. That's because every program has to be started by some other program. Child processes inherit env vars from their parent.

