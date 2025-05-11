require "http/client"
require "json"

response = HTTP::Client.get("https://api.imgflip.com/get_memes")
data = JSON.parse(response.body)
meme = data["data"]["memes"][0]

name = meme["name"].to_s
url = meme["url"].to_s

puts "Meme: #{name}"
puts "URL: #{url}"
