task :default => :build

desc "Clean up generated site"
task :clean do
  cleanup
end

namespace :compile do
  desc "Compile stylesheets"
  task :stylesheets do
    sass ''
  end
end

desc "Build stylesheets and static site"
task :build => :clean do
  jekyll 'build'
end

desc "Serve _site on localhost:4000"
task :serve do
  start_server
end

desc "Deploy _site to host"
task :deploy do

end

private

def cleanup
  sh 'rm -rf _site'
end

def jekyll(opts = '')
  sh 'jekyll ' + opts
end

def sass(opts = '')
  sh 'sass ' + opts
end

def start_server
  sh 'ruby -run -e httpd _site -p5000'
end
