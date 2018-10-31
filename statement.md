# description: 
 The code is ill-formed.  Non-const member functions can not be called on const objects.

```C++ runnable
#include <iostream>

struct Foo
{
  Foo() {} 

  void go()
  {
    std::cout << "Foo" << std::endl;
  }
};

struct Bar : public Foo
{
  Bar() {}

  void go()
  {
    std::cout << "Bar" << std::endl;
  }
};

int main(int argc, char** argv) 
{ 
  Bar b;

  const Foo f = b;

  f.go();

  return 0; 
}
