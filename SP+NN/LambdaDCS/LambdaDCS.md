### **Learning dependency-based compositional semantics.** *Percy Liang et al.* **ACL, 2011** [(PDF)](./DCS.pdf) [(arXiv)](https://direct.mit.edu/coli/article/39/2/389/1439/Learning-Dependency-Based-Compositional-Semantics) (Citations 638)
  * tree-structured logical forms
  * not as expressive as lambda calculus
### **Lambda Dependency-Based Compositional Semantics.** *Percy Liang.* **ACL, 2013** [(PDF)](./lambdaDCS.pdf) [(arXiv)](https://arxiv.org/abs/1309.4408) (Citations 115)
  * 主题：提出一种比lambda演算（λ-Calculas）更紧凑、更简单的LF表达式
    * Utterance: “people who have lived in Seattle”
    * Logical form (lambda calculus): λx.∃e.PlacesLived(x, e) ∧ Location(e, Seattle)
    * Logical form (lambda DCS): PlacesLived.Location.Seattle
  * *注：PlacesLived()是Freebase里的复合值类型（compound value types，CVT；类似C语言结构体，亦等同于我们自己定义的复合结构），location()是PlacesLived(e, Seattle)中的一个子属性；并列的子属性还有比如StartDate(e, ·) and EndDate(e, ·)*
  * 语法：
    * **Unary base case**
      * λ-DCS：Seattle
      * λ-Calculas：λx.[x = Seattle], [condition]表示条件真值，当且仅当x=3时返回true
    * **Binary base case**
      * λ-DCS：PlaceOfBirth
      * λ-Calculas：λx.λy.PlaceOfBirth(x, y)
    * **Join**
      * people born in Seattle”
        * λ-DCS：PlaceOfBirth.Seattle
        * λ-Calculas：λx.PlaceOfBirth(x, Seattle)
      * “those who had children born in Seattle”
        * λ-DCS：Children.PlaceOfBirth.Seattle
        * λ-Calculas：λx.∃y.Children(x, y) ∧ PlaceOfBirth(y, Seattle)
    * **Intersection**
      * "scientists born in Seattle"
        * λ-DCS：Profession.Scientist ⊓ PlaceOfBirth.Seattle
        * λ-Calculas：λx.Profession(x, Scientist) ∧ PlaceOfBirth(x, Seattle)
    * **Union**
      * “Oregon, Washington and Canadian provinces”
        * λ-DCS：Oregon ⊔ Washington ⊔ Type.CanadianProvince
        * λ-Calculas：λx.[x = Oregon] ∨ [x = Washington] ∨ Type(x, CanadianProvince).
    * **Negation**
      * “states not bordering California”
        * λ-DCS：Type.USState ⊓ ¬Border.California
        * λ-Calculas：λx.Type(x, USState) ∧ ¬Border(x, California)
    * **Higher-order functions**
      * "the number of states"
        * λ-DCS：count(Type.USState)
        * λ-Calculas：count(λx.Type(x, USState))
      * "the number largest state by area"
        * λ-DCS：argmax(Type.USState, Area)
        * λ-Calculas：argmax(λx.Type(x, USState), λx.λy.Area(x, y))
    * **Lambda abstraction**
      * “those who had a child who influenced them”
        * λ-DCS：μx.Children.Influenced.x
        * λ-Calculas：λx.∃y.Children(x, y).Influenced(y, x)
      * ”person who has the most children”
        * λ-DCS：argmax(Type.Person, R[λx.count(R[Children].x])), 【R[b]】 = λy.λx.【b】(x, y)
        * λ-Calculas：argmax(λx.Type(x, Person), λx.count(λz.Children(x, z)))