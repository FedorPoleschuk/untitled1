# В лесу родилась елочка

## Шаг 1

Подойдите к вашему агенту чтобы дать ему блок. Не можете найти агента? Добавьте команду чата с блоком ``||agent: агент телепортроваться к игроку||``
```blocks
player.onChat("тп", function () {
    agent.teleportToPlayer()
    })
```
## Шаг 2
Добавьте еше один блок ``||player: при команде чата||``  с названием **"елочка"**.

```blocks
player.onChat("елочка", function () {

})

```
## Шаг 3
Вставьте внутрь обработчика событий блок ``||agent: агент ставит блок или предмет||`` со значением **"саженец сосны"** в количестве **"1"** в **"1"**

```blocks
player.onChat("елочка", function () {
    agent.setItem(SPRUCE_SAPLING, 1, 1)
})

```
## Шаг 4
Повторите действия но уже с **"костной мукой"** в количестве 10 в 2
```blocks
player.onChat("елочка", function () {
    agent.setItem(SPRUCE_SAPLING, 1, 1)
    agent.setItem(BONE_MEAL, 10, 2)
})

```

## Шаг 5
Добавьте движение агенту для того чтобы он разместил саженец сосны перед собой при помощи  ``||agent: разместить вперед || ``
```blocks
player.onChat("елочка", function () {
    agent.setItem(SPRUCE_SAPLING, 1, 1)
    agent.setItem(BONE_MEAL, 10, 2)
    agent.place(FORWARD)
})

```

## Шаг 6
Измените активную ячейку на **"2"** и повторите действия с костной мукой
```blocks
player.onChat("елочка", function () {
    agent.setItem(SPRUCE_SAPLING, 1, 1)
    agent.setItem(BONE_MEAL, 10, 2)
    agent.place(FORWARD)
    agent.setSlot(2)
    agent.place(FORWARD)
})

```
## Шаг 7
Перейдите в Minecraft, нажмите клавишу **"T"** и введите команду **"елочка"**

## Шаг 8
От одной муки ничего не произошло? Разместите  ``||loops: повторить || `` для удобрения саженца 10 раз
```blocks
player.onChat("елочка", function () {
    agent.setItem(SPRUCE_SAPLING, 1, 1)
    agent.setItem(BONE_MEAL, 10, 2)
    agent.place(FORWARD)
    agent.setSlot(2)
    for (let index = 0; index < 9; index++) {
        agent.place(FORWARD)
        }
})

```
## Шаг 9
Ура!!! Агент сажает и выращивает елочку! Проверить это при помощи команды чата **"елочка"**
## Шаг 10
Теперь задача для закрепления добавьте трусишку зайку серого и сердитого волка около елочки