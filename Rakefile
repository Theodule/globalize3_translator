require 'rake'
require 'rake/testtask'
require 'rake/rdoctask'
require 'lib/globalize/translator/version'

desc 'Default: run unit tests.'
task :default => :test

desc 'Test the globalize3_translator plugin.'
Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.libs << 'test'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
end

desc 'Generate documentation for the globalize3_translator plugin.'
Rake::RDocTask.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'Globalize3Translator'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('README')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

desc 'Build gem'
task :build do
  system "gem build globalize3_translator.gemspec"
end
 
desc 'Release gem'
task :release => :build do
  system "gem push globalize3_translator-#{Globalize::Translator::VERSION}.gem"
end
