## Phalcon micro starter

[![Latest Stable Version](https://poser.pugx.org/langaner/phalcon-micro-starter/v/stable)](https://packagist.org/packages/langaner/phalcon-micro-starter)
[![Total Downloads](https://poser.pugx.org/langaner/phalcon-micro-starter/downloads)](https://packagist.org/packages/langaner/phalcon-micro-starter)
[![Latest Unstable Version](https://poser.pugx.org/langaner/phalcon-micro-starter/v/unstable)](https://packagist.org/packages/langaner/phalcon-micro-starter)
[![License](https://poser.pugx.org/langaner/phalcon-micro-starter/license)](https://packagist.org/packages/langaner/phalcon-micro-starter)

A Skeleton project what include jwt token authentication.

## How to install

Run `composer create-project langaner/phalcon-micro-starter project-directory --prefer-source` or download zip.

## Folders

Controllers - all your app controllers

Middleware - collection of middleware

Models - models folder

Presenters - presenters. You can use it by call it from model $this->userRepository->getModel()->getPresenter()->test

Providers - all app providers

Repositories - all repositoreis. You can use it by call $this->userRepository->test()

Services - all app services. You can use it by call $this->userService->test()

routes - all routes. You can separate it to files or write all in routes.php

## Routes

http://servarname.server/auth/login - login route. This route provide user auth return his token. All routes protected with AuthMiddleware. Auth settings located in auth config file.

## Bindings

To use repositories, services, presenters you must register binding in AppProvider to it.

Examples:

Repository - $this->bindRepository('userRepository', UserRepository::class, [new UserModel]);

Service - $this->bindService('userService', UserService::class, [$this->getDi()->get('userRepository')]);

Presenter - $this->bindRepository('userPresenter', UserPresenter::class, [new UserModel]);
