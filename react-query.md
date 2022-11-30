## React query
### useQuery
> Document: https://react-query-v3.tanstack.com/reference/useQuery

### enabled: 
#### Use case: 
- Chúng ta không muốn query được run tự động khi component được render
- Chúng ta muốn query đó sẽ đc run khi có 1 event xảy ra, ví dụ click vào button submit
#### Solution của mình
- Set enabled = false 
- Dùng hàm refetch trong handler của event

Ví dụ: 
```
export const use.... = () => {
    const {
        data,
        isLoading,
        ...props
    } = useQuery(["id"], {
        enabled: false,
        refetchOnMount: false,
        refetchInterval: false,
        queryFn: query function here
    });

    return { data, isLoading, ...props };
};

> vẫn chạy đc nhưng có vẻ không phải là giải pháp đúng
```
### Solution của reviewer
- set enabled = isEnabled và ở chỗ dùng use query thì truyền giá trị vào isEnabled cho nó.
- trong event handler thì update lại giá trị của is enabled

### WHY: unknow 
=> action: reseach


### refech 

#### Use case: 
- Chúng ta cần refech data khi quay lại component/page đó

#### Solution của mình
- dùng hàm refech on mount 
- Ví dụ: 
```
useEffect(() => {refechData() }, [])
```
> vẫn chạy đc nhưng có vẻ không phải là giải pháp đúng


### Solution của reviewer
- trong useQuery có 1 tham số là refetchOnMount, default value là true
- Data sẽ rự động refech khi component mount

#### Action
- Còn một số options nữa, liên quan đến refech cần phải xem lại docs cho kỹ



