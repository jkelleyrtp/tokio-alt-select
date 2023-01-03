# Alt-select: an alternative tokio::select macro that supports rustfmt

A macro to make `tokio::select!` more ergonomic.

This macro is a drop-in replacement for `tokio::select!` that works exactly the same, but
supports rustfmt. It uses closure syntax which rustfmt supports with support for `if branches` and
the "biased" keyword.

```rust
select!(
    biased,
    tasks.join_next(),
    |task| if (!ready) {
        // ...
    },
    title.changed(),
    |title| {
        // ...
    }
)
```



## Contributing

- Report issues on our [issue tracker](https://github.com/jkelleyrtp/tokio-alt-select/issues).

## License
This project is licensed under the [MIT license].

[mit license]: https://github.com/jkelleyrtp/tokio-alt-select/blob/master/LICENSE

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in tokio-alt-select by you, shall be licensed as MIT, without any additional
terms or conditions.
