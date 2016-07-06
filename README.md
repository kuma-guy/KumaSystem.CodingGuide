# KumaSystem.CodingGuide

## PHP

### __invoke() or ()

アプリケーションコードでは()
ライブラリコードでは、__invoke()を使用する。

## BEAR.Resource

### Embed or ResourceInject & GET

できる限り、Embedに寄せる。


###  Resource Response

#### In case for returning multiple resources

必要でない場合を除き、明示的に名前を指定しない。


*BAD*
```PHP
$this['comments'] = get_comments();
return $this;
```

*BETTER*
```PHP
$this->body = get_comments();
return $this;
```

リソース利用側のコードがシンプルになる。
```
$comments = $this['comments']()->body;
```

## Ray

### Setter Injection

ライブラリコードでは、Setter Injectionを使用しない。

### Provider束縛

可能な限り避ける。`toConstructor`束縛を検討。



### AvoidConditionalLogicInModules

モジュール内でのConditional logicを避ける。

https://github.com/google/guice/wiki/AvoidConditionalLogicInModules

