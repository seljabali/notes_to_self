- [Alphabetical Operators](https://github.com/ReactiveX/RxJava/wiki/Alphabetical-List-of-Observable-Operators)

- [Operators](http://reactivex.io/documentation/operators.html)

- [RxTutorial](https://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/) [, part 2](https://blog.danlew.net/2014/09/22/grokking-rxjava-part-2/)

- [Fundamentals w/ RxKotlin](https://medium.com/@gabrieldemattosleon/fundamentals-of-rxjava-with-kotlin-for-absolute-beginners-3d811350b701)

- [RxJava wiki](https://github.com/ReactiveX/RxJava/wiki)

- [RxRelay](https://github.com/JakeWharton/RxRelay)

- [Event Bus](https://medium.com/@FerRaviola/rxandroid-an-event-bus-on-steroids-9699e93eca98)

- [Compose](https://blog.danlew.net/2015/03/02/dont-break-the-chain/)

- [Subjects](https://proandroiddev.com/rxjava-different-types-of-subjects-ef9183b5e87e)

App Wide Loading Spinner
```
val networkDisposable = api.getUsers()
                           .subscribeOn(io)
			   .observeOn(main)
			   .subscribe { users-> ...}

val loadingSpinner = CompositeDisposable()
loadingSpinner.add(network)

sideffect to a behavior relay, to which your call sites subscribe to

or share refcounted+replayed observable directly, but beware first subscirber will launch it
```
