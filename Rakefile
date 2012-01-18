namespace :jekyll do

  desc 'Delete generated _site files'
  task :clean do
    system 'rm -rf _site'
  end

  desc 'Run the local jekyll server'
  task :server do
    system 'jekyll --server --auto'
  end

  desc 'Clean, compile and run the server'
  task :compile => [:clean] do
    system 'jekyll'
  end
end

namespace :sass do

  desc 'Delete compiled CSS files'
  task :clean do
    system 'rm -rf .sass-cache/'
    system 'rm -rf _site/stylesheets/*'
  end

  desc 'Compile CSS and watch for changes'
  task :watch do
    system 'mkdir -p _site/stylesheets'
    system 'sass --watch _sass/screen.scss:_site/stylesheets/screen.css'
  end

  desc 'Compile CSS'
  task :compile => [:clean] do
    system 'mkdir -p _site/stylesheets'
    system 'sass _sass/screen.scss:_site/stylesheets/screen.css'
  end
end

namespace :post do

  desc 'Generate a new, properly formated post file'
  task :draft, [:title] do |t, args|
    title = args.title || 'draft'
    filename = "#{Time.now.strftime('%Y-%m-%d')}-#{title}.markdown"
    system "echo > _drafts/#{filename}"
  end
end
