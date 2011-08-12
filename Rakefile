desc 'create a new draft post'
task :post do
  title = ENV['TITLE']
  post_date = Time.new
  slug = "#{post_date.strftime('%Y-%m-%d')}-#{title.downcase.gsub(/[^\w]+/, '-')}"

  file = File.join(
    File.dirname(__FILE__),
    '_posts',
    slug + '.markdown'
  )

  File.open(file, "w") do |f|
    f << <<-EOS.gsub(/^    /, '')
    ---
    layout: post
    title: #{title}
    published: false
    categories:
    ---

    EOS
  end

  system ("#{ENV['EDITOR']} #{file}")
end

desc "Deploy."
task :deploy => %w(deploy:before deploy:push deploy:after)

desc "Set up deployment prerequisites."
task "deploy:newb" do
  %w(heroku taps).each do |gem|
    puts "sudo gem install #{gem}" unless Gem.available? gem
  end

  Deploy::ENVIRONMENTS.each do |branch, env|
    unless /^#{env}/ =~ `git remote`
      puts "git remote add #{env} git@heroku.com:myapp-#{env}.git"
      #puts "git remote add #{env} git@heroku.com:myapp-#{env}.git"
      puts "git fetch #{env}"

      unless /#{branch}$/ =~ `git branch`
        puts "git branch #{branch} origin/#{env}"
      end
    end
  end
end

