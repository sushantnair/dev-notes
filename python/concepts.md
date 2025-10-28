1. # [Singleton classes](https://medium.com/gitconnected/backend-interview-question-implement-a-singleton-in-python-4f5af8b7e160)
* A singleton class will only have ONLY ONE instance. If we attempt to instantiate another instance, we simply get back the same singular instance.
* This is useful if we only need one instance of a class or multiple instances of a class is not desirable
* For instance, let’s say we only want one singular database connection per application. We don’t want to create a new database connection every time we need to use it as having multiple database connections open at the same time might lead to a waste of resources or even conflicts.
```python
class DBConnection:
    instance = None

    def __new__(cls):
        
        # if cls.instance does not exist, instantiate it
        if not cls.instance:
            cls.instance = super().__new__(cls)

        # else, simply return the existing instance
        return cls.instance
# here, we override the __new__ magic method, which defines how a class is instantiated.
# if cls.instance does not exist, we make it exist, and we instantiate one.
# if cls.instance already exists, we simply return the existing instance
# this way, we will only get the instance that is created when cls.instance is None.  
```

   
