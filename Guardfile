# A sample Guardfile
# More info at https://github.com/guard/guard#readme

# Add files and commands to this file, like the example:
#   watch(%r{file/path}) { `command(s)` }
#
require "open3"
require "colorize"

guard 'shell' do
  watch(/(.*).pm/) do |m|
    arr = Open3.capture3("perl -c #{m[0]}")
    line = arr.first.split("\n").first
    unless line =~ /syntax OK/
      puts line.red
    else
      puts line.green
    end
  end
end
