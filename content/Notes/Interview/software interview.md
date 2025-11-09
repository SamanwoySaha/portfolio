---
title: software interview
draft: true
tags:
date: 30-Aug-2025
---


online cloud reading application 
similar to amazon kindle (for short stories)
we need help designing actual application (code that implements this)

few things looking for:
- users have a library of books that they can add to or remove from
- users can set a book from their library as active
- the reading application remembers where  a user left off in given book
- the reading application only displays a page of text at a time in the active book.

- all books in library
- remember active book
- remember last pages in all books
- display a page in active book

classes
- representing a book
	- id: str/int ?
	- title: str
	- pages/content in the book: list of strings (per page)
	- last page user looked at: int (remember off-by-one)
- representing a library
	- collection of books {id: Book()}
	- active book: variable correspond to id

```python
class Book:
	def __init__(self, id, title, content):
		self.id = id
		self.title = title
		self.content = content # now just a long string of chars
		self.last_page = 0
		
		self.font_size = 12
		self.chars_per_page = calculate(self.font_size)
		
	def display_page(self):
		start_idx = self.chars_per_page * self.last_page
		end_idx = start_idx + self.chars_per_page
		return self.content[start_idx: end_idx]
		# return self.content[self.last_page]
		
	def turn_page(self):
		self.last_page += 1
		return self.display_page()
		
# class Display:

# class UserBook:
		
class Library:
	def __init__(self):
		self.collection = dict()
		self.active_book = None
		self.id_counter = 0
		
	def add_to_collection(self, Book):
		new_book = Book(self.id_counter, title, content)
		self.collection[new_book.id] = new_book
		self.id_counter += 1
		
	def remove_from_collection(self, id):
		del self.collection[id]
		
	def set_active_book(self, id):
		self.active_book = id
		
	def display_page(self):
		self.collection[self.active_book].display_page()
		
	def turn_page(self):
		return self.collection[self.active_book].turn_page()
```