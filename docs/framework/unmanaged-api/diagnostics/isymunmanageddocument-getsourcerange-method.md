---
title: "ISymUnmanagedDocument::GetSourceRange メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dcddebbca74bb94bd2411038a02b900b2f64f2d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange メソッド
指定されたバッファーに埋め込まれたソースの指定した範囲を返します。 バッファーは、ソースを保持するのに十分な大きさである必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `startLine`  
 [in]現在のドキュメント内の開始行。  
  
 `startColumn`  
 [in]現在のドキュメント内の開始列。  
  
 `endLine`  
 [in]現在のドキュメント内の最終行。  
  
 `endColumn`  
 [in]現在のドキュメント内の最終列。  
  
 `cSourceBytes`  
 [in](バイト単位)、ソースのサイズ。  
  
 `pcSourceBytes`  
 [out]ソースのサイズを受け取る変数へのポインター。  
  
 `source`  
 [out]サイズ (バイト単位)、ソース ドキュメントの指定された範囲の長さ。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK です。  
  
## <a name="see-also"></a>参照  
 [ISymUnmanagedDocument インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
