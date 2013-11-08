require "rubygems"
require "rake"

desc "Start Sass so that is compiles to css upon file save"
task :sass do
  system "sass --watch jekyll_site/assets/sass:jekyll_site/assets/css"
end # task :sass

desc "Start Sass so that is compiles to css upon file save"
task :minify do
  system "sass --watch jekyll_site/assets/sass:jekyll_site/assets/css --style compressed"
end # task :minify