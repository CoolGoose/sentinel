### Users

The user repository can be accessed using `Sentinel::getUserRepository()` and allows you to manage users using Sentinel.

> **Note 1** You can use the following methods directly on the Sentinel facade without the `getUserRepository` part. Example `Sentinel::findById(1)` instead of `Sentinel::getUserRepository()->findById(1)`.

> **Note 2** You can add the word `User` between `find` and the method name and drop the `getUserRepository` call. Example `Sentinel::findUserByCredentials` instead of `Sentinel::getUserRepository()->findByCredentials`.

#### Sentinel::findById()

Find a user by id.

```php
$user = Sentinel::findById(1);
```

#### Sentinel::findByCredentials()

Find a user by credentials.

```php
$credentials = [
	'email'    => 'john.doe@example.com',
	'password' => 'password',
];

$user = Sentinel::findByCredentials($credentials);
```

#### Sentinel::findByPersistenceCode()

Find a user by persistence code.

```php
$user = Sentinel::findByPersistenceCode('persistence_code_here');
```

#### Sentinel::validateCredentials()

Validates a user's credentials.

```php
$credentials = [
	'email'    => 'john.doe@example.com',
	'password' => 'password',
];

$user = Sentinel::validateCredentials($credentials);
```

#### Sentinel::validForCreation()

Validates a user for creation.

```php
$credentials = [
	'email'    => 'john.doe@example.com',
	'password' => 'password',
];

$user = Sentinel::validForCreation($credentials);
```

#### Sentinel::validForUpdate()

Validates a user for update.

```php
$user = Sentinel::findById(1);

$credentials = [
	'email'    => 'new.john.doe@example.com',
];

$user = Sentinel::validForUpdate($user, $credentials);
```

#### Sentinel::create()

Creates a new user.

```php
$credentials = [
	'email'    => 'john.doe@example.com',
	'password' => 'password',
];

$user = Sentinel::create($credentials);
```

#### Sentinel::update()

Updates an existing user.

```php
$user = Sentinel::findById(1);

$credentials = [
	'email'    => 'new.john.doe@example.com',
];

$user = Sentinel::update($user, $credentials);
```

#### Sentinel::setHasher()

Sets the hasher.

```php
Sentinel::setHasher(new Cartalyst\Sentinel\Hashing\WhirlpoolHasher);
```

#### Sentinel::createModel()

Creates a new user model instance.

```php
$user = Sentinel::createModel();
```

#### Sentinel::setModel()

Sets the user model.

```php
Sentinel::setModel('Your\User\Model');
```