
import 'dart:io';

mixin ActivityLogger {
  void logActivity(String message) {
    print('[ACTIVITY] $message');
  }
}

abstract class LibraryItem {
  final int id;
  final String title;
  bool isBorrowed;

  LibraryItem({
    required this.id,
    required this.title,
    this.isBorrowed = false,
  });

  void displayInfo();
}

class Book extends LibraryItem with ActivityLogger {
  final String author;

  Book({
    required int id,
    required String title,
    required this.author,
  }) : super(id: id, title: title);

  @override
  void displayInfo() {
    String status = isBorrowed ? 'Borrowed' : 'Available';

    print(
      'ID: $id | Title: $title | Author: $author | Status: $status'
    );
  }
}

class LibraryMember {
  final int memberId;
  final String name;

  LibraryMember({
    required this.memberId,
    required this.name,
  });
}

class Library with ActivityLogger {
  final List<Book> books = [];

  void addBook(Book book) {
    books.add(book);
    logActivity('"${book.title}" was added to the library.');
  }

  void displayBooks() {
    print('\n========== LIBRARY BOOKS ==========');

    if (books.isEmpty) {
      print('No books available.');
      return;
    }

    for (Book book in books) {
      book.displayInfo();
    }
  }

  Future<void> borrowBook(
      int bookId, LibraryMember member) async {

    print('\nProcessing borrowing request...');

    await Future.delayed(Duration(seconds: 2));

    try {
      Book book = books.firstWhere(
        (item) => item.id == bookId,
        orElse: () => throw Exception('Book not found.'),
      );

      if (book.isBorrowed) {
        throw Exception('This book is already borrowed.');
      }

      book.isBorrowed = true;

      logActivity(
        '${member.name} borrowed "${book.title}".'
      );

      print('Successfully borrowed "${book.title}"!');

    } catch (error) {
      print('Borrowing failed: $error');
    }
  }

  Future<void> returnBook(
      int bookId, LibraryMember member) async {

    print('\nProcessing return request...');

    await Future.delayed(Duration(seconds: 2));

    try {
      Book book = books.firstWhere(
        (item) => item.id == bookId,
        orElse: () => throw Exception('Book not found.'),
      );

      if (!book.isBorrowed) {
        throw Exception('This book is not borrowed.');
      }

      book.isBorrowed = false;

      logActivity(
        '${member.name} returned "${book.title}".'
      );

      print('Successfully returned "${book.title}"!');

    } catch (error) {
      print('Returning failed: $error');
    }
  }
}

Future<void> main() async {

  Library library = Library();

  LibraryMember member = LibraryMember(
    memberId: 1,
    name: 'Student',
  );

  // Sample books
  library.addBook(Book(
    id: 1,
    title: 'Introduction to Dart',
    author: 'John Smith',
  ));

  library.addBook(Book(
    id: 2,
    title: 'Object-Oriented Programming',
    author: 'Jane Cruz',
  ));

  bool isRunning = true;

  print('\n====================================');
  print('       LIBRARY MANAGEMENT SYSTEM');
  print('====================================');

  print('Welcome, ${member.name}!');

  while (isRunning) {

    print('\n--------------- MENU ---------------');
    print('1. Add a Book');
    print('2. View All Books');
    print('3. Borrow a Book');
    print('4. Return a Book');
    print('5. Exit');

    stdout.write('Enter your choice: ');

    String? choice = stdin.readLineSync();

    switch (choice) {

      case '1':
        stdout.write('Enter book title: ');
        String title = stdin.readLineSync() ?? '';

        stdout.write('Enter author name: ');
        String author = stdin.readLineSync() ?? '';

        if (title.trim().isEmpty || author.trim().isEmpty) {
          print('Title and author cannot be empty.');
          break;
        }

        int newId = library.books.isEmpty
            ? 1
            : library.books
                .map((book) => book.id)
                .reduce((a, b) => a > b ? a : b) + 1;

        library.addBook(Book(
          id: newId,
          title: title,
          author: author,
        ));

        print('Book added successfully!');
        break;

      case '2':
        library.displayBooks();
        break;

      case '3':
        stdout.write('Enter Book ID to borrow: ');

        int? borrowId = int.tryParse(
          stdin.readLineSync() ?? ''
        );

        if (borrowId == null) {
          print('Invalid Book ID.');
          break;
        }

        await library.borrowBook(borrowId, member);
        break;

      case '4':
        stdout.write('Enter Book ID to return: ');

        int? returnId = int.tryParse(
          stdin.readLineSync() ?? ''
        );

        if (returnId == null) {
          print('Invalid Book ID.');
          break;
        }

        await library.returnBook(returnId, member);
        break;

      case '5':
        isRunning = false;
        print('\nThank you for using the Library Management System!');
        break;

      default:
        print('Invalid choice. Please select 1-5.');
    }
  }
}
