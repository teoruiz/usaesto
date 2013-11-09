require "rubygems"
require "rake"

source_dir = "jekyll_site"

desc "Start Sass so that is compiles to css upon file save"
task :sass do
  system "sass --watch #{source_dir}/assets/sass:#{source_dir}/assets/css"
end # task :sass

desc "Start Sass so that is compiles to css upon file save"
task :minify do
  system "sass --watch #{source_dir}/assets/sass:#{source_dir}/assets/css --style compressed"
end # task :minify

desc "Build production snapshot of the site"
task :build do
	system "sass --update #{source_dir}/assets/sass:#{source_dir}/assets/css --style compressed --force"
	system "jekyll build -s #{source_dir} --config #{source_dir}/_config.yml,#{source_dir}/_config_production.yml"
end

desc "Run development server"
task :serve do
	jekyllPid = Process.spawn("jekyll serve -s #{source_dir} --watch")
	sassPid = Process.spawn("sass --watch #{source_dir}/assets/sass:#{source_dir}/assets/css")

	trap("INT") {
		[jekyllPid, sassPid].each { |pid| Process.kill(9, pid) rescue Errno::ESRCH }
		exit 0
	}

	[jekyllPid, sassPid].each { |pid| Process.wait(pid) }
end

