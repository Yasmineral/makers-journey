# Unit Testing
Unit tests are the code you write to test your code. They provide you with reassuarance that everything works as it should, and help to guard against introducing future errors. Just as a chef needs to test the food they make to be sure it’s good enough to serve to their guests, you need to write unit tests in order to ensure that your code is of high quality.

At a high level, unit testing is about testing individual methods or areas (units) of your code to ensure that they do what you expect them to do. For any given unit of code, your unit tests allow you to ensure that, given a certain set of inputs, the output is as you expect.

**Arrange, Act, Assert**

Example. Notice that the unit test is split into three distinct sections:

```describe FileSystem do
  it 'can add items to storage' do
    # Arrange
    file_system = FileSystem.new
    file = File.new

    # Act
    file_system.store(file)

    #Assert
    expect(file_system.storage).to include(file)
  end
end
```

This is a common pattern which many of your unit tests will follow. First you Arrange all the preconditions required for your code to run - creating any objects that you’re going to need. Next, you act or execute the code which needs to be run in order for your assertion to be true. Finally, you make the assertion itself.
