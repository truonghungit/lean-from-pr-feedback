### Tránh render false trng className

#### Use case
- Chúng ta muốn render 1/nhiều class khi thỏa điều kiện
- Ví dụ
```
className={`${isEnabled && "enabled-class"}`}
```
#### Reviewer Solution
```
className={isEnabled && "enabled-class" }
```
