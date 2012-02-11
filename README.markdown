# jekyll.vim

Blogging from the command line should not be tedious.

This script is intended to automate the process of creating and editing
[Jekyll](http://jekyllrb.com/) blog posts from within
[vim](http://www.vim.org/).

This is a complete rewrite of
[csexton/jekyll.vim](https://github.com/csexton/jekyll.vim/) with these
improvements:

* Commands are added as buffer commands when a Jekyll blog is found
* Commands to edit/split/vsplit/tabnew a post
* Tab completion for opening existing posts
* Recognizes Octopress blogs and others with custom `_posts` directory
* Customizable template for new posts
* Customizable build command, with automatic support for bundler

## Commands

The `:Jpost` (Jekyll post) command is used to create and edit blog posts. It
has variants for opening a post in a horizontal or vertical split or a new
tab. Call with a bang, (eg: `:Jpost!`) to create a new post. Call without a
bang (eg: `:Jpost`) to edit a post. The `:Jbuild` command can be used to build
a blog.

    :Jpost[!]  [{name}] Create or edit the specified post. With no argument,
                        you will be prompted to select a post or enter a title.

    :JSpost[!] [{name}] Same as :Jpost, but opens post in a horizontal split.

    :JVpost[!] [{name}] Same as :Jpost, but opens post in a vertical split.

    :JTpost[!] [{name}] Same as :Jpost, but opens post in a tab.

    :Jbuild    [{args}] Generate blog. This will check for the presence of a
                        Gemfile; if found `bundle exec` is used to run the
                        `jekyll` command. The blog will be built with:

                jekyll --no-auto --no-server BLOG_ROOT BLOG_ROOT/SITE_DIR <args>

                        If this doesn't fit your situation, you can set a
                        custom command with `g:jekyll_build_command`. When
                        using a custom command no check for a Gemfile is
                        performed.

See also `:help jekyll-commands`.

## Configuration

See `:help jekyll-configuration`.

## License

Same as Vim itself, see `:help license`.
