2017/11/09
## Prefabの管理方法
### 1. リストで
```
public GameObject Prefab;

/* Prefabを格納するリストを作成 */
List<GameObject> goList = new List<GameObject>();

void Start()
{
    /* Prefabを10個生成 */
    for(int i = 0; i < 10; i++)
    {
        GameObject go = Instantiate(Prefab);    //Prefabを生成
        goList.Add(go);    //作成したオブジェクトをリストに追加
    }
    /* リストの0番目の座標を指定 */
    goList[0].transform.position = new Vector3(1.0f, 1.0f, 1.0f);
}

void Update()
{
    
}
```
