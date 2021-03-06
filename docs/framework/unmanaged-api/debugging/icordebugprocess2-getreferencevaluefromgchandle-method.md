---
title: "ICorDebugProcess2::GetReferenceValueFromGCHandle メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ac4cc32be6914ea858d32b8699a695588f0a1e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle メソッド
ガベージ コレクション ハンドルを持つ指定したマネージ オブジェクトへの参照へのポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `handle`  
 [in]ガベージ コレクション ハンドルを持つマネージ オブジェクトへのポインター。 この値は、<xref:System.IntPtr>オブジェクトをから取得できる、<xref:System.Runtime.InteropServices.GCHandle>管理オブジェクト。  
  
 `pOutValue`  
 [out]指定したマネージ オブジェクトへの参照を表す ICorDebugReferenceValue オブジェクトのアドレスへのポインター。  
  
## <a name="remarks"></a>コメント  
 ガベージ コレクションの参照値を持つ返される参照値を混同しないでください。  
  
 返される参照は、通常の参照のように動作します。 コードの実行がブレークポイントの後に継続するには無効です。 ターゲット オブジェクトの有効期間は参照値の有効期間の影響を受けません。  
  
> [!NOTE]
>  `GetReferenceValueFromGCHandle`メソッドは、ハンドルは検証されません。 したがって、`GetReferenceValueFromGCHandle`デバッガーと無効なハンドルが渡された場合にデバッグ中のコードの両方、メソッドは破損可能性があることができます。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
