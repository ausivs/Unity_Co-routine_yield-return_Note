# Unity_Co-routine_yield-return_Note
**コルーチンの yield return ... についての簡易メモ**

```c#
public class Hoge : MonoBehaviour {

	// Use this for initialization
	void Start () {
		StartCoroutine("Coroutine");
	}
	
	// Update is called once per frame
	void Update () {
		Debug.Log ("アップデート");
	}

	//　1ループ毎に、中断する
	IEnumerator Coroutine(){
		for (int i = 0; i < 5; i++) {
		    Debug.Log (i);
		    yield return null;
		}
    	}
	/*
	//　全ループ終了後に、中断する
	IEnumerator Coroutine(){
		for (int i = 0; i < 5; i++) {
		    Debug.Log (i);
		}
	    	yield return null;
	}
	*/
}
```

Startで最初にコルーチンを実行します。
<br>
```yield return null;```が入ると一度中断して次のフレームで再度再開します。
<br>
デバッグコンソールを見るとわかると思います。
