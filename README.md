#Rails で ToDo Appを作成

■参考
https://medium.com/@deallen7/how-to-build-a-todo-app-in-rails-e6571fcccac3



■SQLite3::ConstraintException: FOREIGN KEY constraint failed: DELETE FROM "todo_lists" WHERE のエラー
https://ja.stackoverflow.com/questions/41525/rails%E3%81%A71%E5%A4%9A%E3%81%AE%E3%83%A2%E3%83%87%E3%83%AB%E3%82%92%E6%B6%88%E3%81%99%E9%9A%9B%E3%81%AB%E3%82%A8%E3%83%A9%E3%83%BC%E3%81%8C%E5%87%BA%E3%82%8B

`/app/models/todo_list.rb` を修正
```
class TodoList < ApplicationRecord
  has_many :todo_items
end
↓
class TodoList < ApplicationRecord
  has_many :todo_items, dependent: :destroy
end
```
