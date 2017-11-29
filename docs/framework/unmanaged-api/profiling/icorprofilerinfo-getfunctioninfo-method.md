---
title: "ICorProfilerInfo::GetFunctionInfo メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetFunctionInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 859887d25e33b4780920ed688684c22031eac16c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="8bb37-102">ICorProfilerInfo::GetFunctionInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="8bb37-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="8bb37-103">指定した関数の親クラスとメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8bb37-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb37-104">構文</span><span class="sxs-lookup"><span data-stu-id="8bb37-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bb37-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bb37-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8bb37-106">[in]親クラスとメタデータ トークンを取得する対象の関数の ID。</span><span class="sxs-lookup"><span data-stu-id="8bb37-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="8bb37-107">[out] 関数の親クラスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8bb37-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="8bb37-108">[out] 関数の親クラスが定義されているモジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8bb37-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="8bb37-109">[out] 関数のメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8bb37-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bb37-110">コメント</span><span class="sxs-lookup"><span data-stu-id="8bb37-110">Remarks</span></span>  
 <span data-ttu-id="8bb37-111">プロファイラー コードを呼び出すことができます[icorprofilerinfo::getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)指定したモジュールのメタデータ インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="8bb37-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="8bb37-112">`pToken` が参照している場所に返されるメタデータ トークンを使用すると、関数のメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8bb37-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="8bb37-113">`ClassID`ジェネリック クラスの関数のできない可能性があります、関数の使用に関する詳細なコンテキスト情報取得できません。</span><span class="sxs-lookup"><span data-stu-id="8bb37-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="8bb37-114">この場合、`pClassId`は 0 になります。</span><span class="sxs-lookup"><span data-stu-id="8bb37-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="8bb37-115">プロファイラーのコードを使用する必要があります[icorprofilerinfo 2::getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)詳細なコンテキストを提供する COR_PRF_FRAME_INFO 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8bb37-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bb37-116">要件</span><span class="sxs-lookup"><span data-stu-id="8bb37-116">Requirements</span></span>  
 <span data-ttu-id="8bb37-117">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="8bb37-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb37-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8bb37-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8bb37-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bb37-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bb37-120">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bb37-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb37-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bb37-121">See Also</span></span>  
 [<span data-ttu-id="8bb37-122">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bb37-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)