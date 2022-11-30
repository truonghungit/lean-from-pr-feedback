### Tránh render false trong className

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


### Custom color của tailwind css
#### Use case
- Chúng ta muốn có màu của border, custom padding, margin, width, height, ... là 1 màu mà không có trong tailwind (maybe)
- Ví dụ
```
<div className="border border-solid border-[#ffffff1a]" />

<div className="mr-6 h-[84px] w-[84px] max-w-[84px] flex-1 rounded-lg border border-solid border-background bg-background shadow-xl">

<div className="mb-3 flex flex-wrap pr-0 md:pr-[30px] lg:mb-0 lg:pr-[30px]">
```

#### Reviewer
- why custom padding of 30 and not follow the tokenized spacing of tailwind?
- why hard-code height & width with magic number of 84 here?
- avoid .5 margins when you can
#### Reviewer Solution
- No suggestion


#### Action
- ....

