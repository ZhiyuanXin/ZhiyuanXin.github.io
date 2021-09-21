task :default => :new

require 'fileutils'

desc "create a new post"
task :new do
  puts "Enter URL of the new post："
    @url = STDIN.gets.chomp
    puts "Enter title: "
    @name = STDIN.gets.chomp
    puts "Enter subtitle: "
    @subtitle = STDIN.gets.chomp
    puts "Enter categories: "
    @categories = STDIN.gets.chomp
    puts "Enter tag: "
    @tag = STDIN.gets.chomp
    @slug = "#{@url}"
    @slug = @slug.downcase.strip.gsub(' ', '-')
    @date = Time.now.strftime("%F")
    @post_name = "_posts/#{@date}-#{@slug}.md"
    if File.exist?(@post_name)
            abort("File already exists. Abort. ")
    end
    FileUtils.touch(@post_name)
    open(@post_name, 'a') do |file|
            file.puts "---"
            file.puts "layout: post"
            file.puts "title: #{@name}"
            file.puts "subtitle: #{@subtitle}"
            file.puts "author: pizida"
            file.puts "date: #{Time.now}"
            file.puts "categories: #{@categories}"
            file.puts "tag: #{@tag}"
            file.puts "---"
    end
    exec "vi #{@post_name}"
end