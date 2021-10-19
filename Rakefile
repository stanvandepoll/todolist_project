require 'rake/testtask'
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

# Add a task to your Rakefile that lists every file in your project except
# those whose names begin with '.' and those that reside in a directory
# whose name begins with '.'

desc 'lists files'
task :files do
  Find.find(File.dirname(__FILE__)) do |path|
    if FileTest.directory?(path)
      if File.basename(path).start_with?('.')
        Find.prune       # Don't look any further into this directory.
      else
        next
      end
    else
      puts path unless File.basename(path).start_with?('.')
    end
  end
end