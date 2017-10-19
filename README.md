**Please note:** This buildpack is an experimental project and is not officially supported.

# .NET Core Buildpack

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpack) for building [.NET Core 2.0.] console apps using [`project.json` files](https://github.com/aspnet/Home/wiki/Project.json-file) and the [.NET CLI](https://github.com/dotnet/cli). Based on https://github.com/noliar/dotnet-buildpack.

## Usage

Example usage:

    $ heroku create --buildpack http://github.com/spuljko/dotnet-buildpack.git
    $ git push heroku master

The buildpack will detect your app as ASP.NET Core if it has `project.json`. If the source code you want to build contains multiple `project.json` files, you can use a [`.deployment`](https://github.com/projectkudu/kudu/wiki/Customizing-deployments) or set a `$PROJECT` config var to control which one is built.

## Attension
1. You should configure a unique compatible framework in `project.json`.
2. Your Project should use `Microsoft.Extensions.Configuration.CommandLine` package.
3. You'd better configure SDK version using `global.json`.