# Use Case Specification

## 1. General Information

* **Use Case Name:** Borrow a book
* **Primary Actor:** Borrower/Reader
* **Secondary Actors:** Librarian, Library System
* **Description:** A client wants to borrow a book from the library, in-person

---

## 2. Preconditions

* The library is open to customers
* The book to be borrowed is available and in the system
* The Library System operates and is accessible to the Librarian
* There is a librarian at the desk

---

## 3. Main Flow

1. The Borrower selects a book from the library collection.
2. The Borrower brings the book to the Librarian.
3. The Librarian requests the Borrower's library card.
4. The Borrower provides identification.
5. The Librarian enters the Borrower's credentials.
6. The Librarian enters the book's identifier.
7. The Library System verifies that the Borrower is eligible to borrow items.
8. The Library System records the loan transaction and assigns a due date.
9. The Library System confirms successful borrowing.
10. The Librarian informs the Borrower of the due date and returns the book to the Borrower.
11. The Borrower leaves with the borrowed book.

---

## 4. Alternative Flows

### 4.1 Borrower is not eligible to borrow

* Step 7 fails (Borrower is not eligible)
* The Library System returns a rejection with the reason.
* The Librarian informs the Borrower that the borrowing request cannot proceed.
* The use case ends without creating a loan.

---

### 4.2 Invalid or unrecognized Borrower identification

* Trigger: Step 5 fails (credentials not found or invalid)
* The Library System rejects the credentials.
* The Librarian informs the Borrower.
* The Borrower may retry with valid identification
  * return to step 4
* If not, the use case ends.

---

## 5. Postconditions

### Success Postconditions

* A loan record exists in the Library System
* The book status is updated to "borrowed"
* The Borrower has the book

---

## 6. Business Rules

* A Borrower may not exceed a maximum number of borrowed books
* A Borrower with overdue items cannot borrow additional books
* A Borrower with unpaid fines above a threshold cannot borrow
* Each book copy can only be loaned to one Borrower at a time
* Loan duration is determined by library policy

---
