require 'html-proofer'

task :test do
  sh "bundle exec jekyll build --future"
  options = {
    assume_extension: true,
    disable_external: true,
    check_html: true,
  }
  HTMLProofer.check_directory("./_site", options).run
end
