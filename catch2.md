# example
#define CATCH_CONFIG_MAIN  // This tells Catch to provide a main() - only do this in one cpp file
#include "catch.hpp"
#include <vector>
unsigned int Factorial( unsigned int number ) {
    return number <= 1 ? number : Factorial(number-1)*number;
}
int getValue(){
    std::vector<int> a(10, 1);
    throw 1;
    return a[11];
}

TEST_CASE( "Factorials are computed", "[factorial]" ) {
    REQUIRE( Factorial(1) == 1 );
    REQUIRE( Factorial(2) == 2 );
    REQUIRE( Factorial(3) == 6 );
    REQUIRE( Factorial(10) == 3628800 );
    REQUIRE_THROWS( getValue());
}
# commands
test.exe -l  # list all run tests
test.exe "*correct digit"  # run with test name ends with "correct digit"
test.exe "[A]" # running test with tag A
test.exe "[A][B]" # running test with tag A and B, if "[A],[B]" means or
> Good test name, like "Encode single upppercase letter --> return correct digit"
REQUIRE_THROWS( expression )
CHECK_THROWS( expression )

REQUIRE_THROWS_AS( expression, type )
CHECK_THROWS_AS( expression, type )

REQUIRE_NOTHROW( expression )
CHECK_NOTHROW( expression )

REQUIRE_THAT(result, matcher expression) # assertions, good functionality to compares string, vector etc
CHECK_THAT(result, matcher expression) 

INFO("Passed first step");  # logging macro
CAPTURE(someValue); #  someValue := 123

## Test fixture (from catch2 github
```
class UniqueTestsFixture {
  private:
   static int uniqueID;
  protected:
   DBConnection conn;
  public:
   UniqueTestsFixture() : conn(DBConnection::createConnection("myDB")) {
   }
  protected:
   int getID() {
     return ++uniqueID;
   }
 };

 int UniqueTestsFixture::uniqueID = 0;

 TEST_CASE_METHOD(UniqueTestsFixture, "Create Employee/No Name", "[create]") {
   REQUIRE_THROWS(conn.executeSQL("INSERT INTO employee (id, name) VALUES (?, ?)", getID(), ""));
 }
 TEST_CASE_METHOD(UniqueTestsFixture, "Create Employee/Normal", "[create]") {
   REQUIRE(conn.executeSQL("INSERT INTO employee (id, name) VALUES (?, ?)", getID(), "Joe Bloggs"));
 }
```

```
TEST_CASE("This is a test"){
    // initialization
    SECTION("Test section 1"){

    }
}
