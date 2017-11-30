---
title: "BeginEnumeration 関数 (アンマネージ API リファレンス)"
description: "BeginEnumeration 関数が列挙体の先頭に、列挙子をリセットします。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginEnumeration
helpviewer_keywords: BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12a742774bff22030bdfaaa34e431059e016a4bf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="07df0-103">BeginEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="07df0-103">BeginEnumeration function</span></span>
<span data-ttu-id="07df0-104">列挙体の先頭に戻るには、列挙子をリセットします。</span><span class="sxs-lookup"><span data-stu-id="07df0-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="07df0-105">構文</span><span class="sxs-lookup"><span data-stu-id="07df0-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="07df0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07df0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="07df0-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="07df0-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="07df0-108">`ptr`[in]ポインター、 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="07df0-108">`ptr` [in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="07df0-109">[in]フラグまたはで説明されている値のビットごとの組み合わせ、[解説](#remarks)列挙体に含まれるプロパティを制御するセクション。</span><span class="sxs-lookup"><span data-stu-id="07df0-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="07df0-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="07df0-110">Return value</span></span>

<span data-ttu-id="07df0-111">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定義する定数として、コード。</span><span class="sxs-lookup"><span data-stu-id="07df0-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="07df0-112">定数</span><span class="sxs-lookup"><span data-stu-id="07df0-112">Constant</span></span>  |<span data-ttu-id="07df0-113">値</span><span class="sxs-lookup"><span data-stu-id="07df0-113">Value</span></span>  |<span data-ttu-id="07df0-114">説明</span><span class="sxs-lookup"><span data-stu-id="07df0-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="07df0-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="07df0-115">0x80041008</span></span> | <span data-ttu-id="07df0-116">フラグの組み合わせ`lEnumFlags`が無効か、無効な引数が指定されました。</span><span class="sxs-lookup"><span data-stu-id="07df0-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="07df0-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="07df0-117">0x8004101d</span></span> | <span data-ttu-id="07df0-118">2 番目の呼び出しに`BeginEnumeration`せずに中間の呼び出しが行われた[ `EndEnumeration`](endenumeration.md)です。</span><span class="sxs-lookup"><span data-stu-id="07df0-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="07df0-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="07df0-119">0x80041006</span></span> | <span data-ttu-id="07df0-120">十分なメモリが新しい列挙体を開始します。</span><span class="sxs-lookup"><span data-stu-id="07df0-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="07df0-121">0</span><span class="sxs-lookup"><span data-stu-id="07df0-121">0</span></span> | <span data-ttu-id="07df0-122">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="07df0-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="07df0-123">コメント</span><span class="sxs-lookup"><span data-stu-id="07df0-123">Remarks</span></span>

<span data-ttu-id="07df0-124">この関数への呼び出しをラップする、 [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="07df0-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="07df0-125">フラグとして渡すことができる、`lEnumFlags`で引数が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="07df0-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="07df0-126">その他のグループから任意のフラグを使って各グループから 1 つのフラグを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="07df0-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="07df0-127">ただし、同じグループにフラグは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="07df0-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="07df0-128">**グループ 1**</span><span class="sxs-lookup"><span data-stu-id="07df0-128">**Group 1**</span></span>

|<span data-ttu-id="07df0-129">定数</span><span class="sxs-lookup"><span data-stu-id="07df0-129">Constant</span></span>  |<span data-ttu-id="07df0-130">値</span><span class="sxs-lookup"><span data-stu-id="07df0-130">Value</span></span>  |<span data-ttu-id="07df0-131">説明</span><span class="sxs-lookup"><span data-stu-id="07df0-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="07df0-132">0x4</span><span class="sxs-lookup"><span data-stu-id="07df0-132">0x4</span></span> | <span data-ttu-id="07df0-133">キーのみを構成するプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="07df0-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="07df0-134">0x8</span><span class="sxs-lookup"><span data-stu-id="07df0-134">0x8</span></span> | <span data-ttu-id="07df0-135">オブジェクト参照のみであるプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="07df0-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="07df0-136">**グループ 2**</span><span class="sxs-lookup"><span data-stu-id="07df0-136">**Group 2**</span></span>

<span data-ttu-id="07df0-137">定数</span><span class="sxs-lookup"><span data-stu-id="07df0-137">Constant</span></span>  |<span data-ttu-id="07df0-138">値</span><span class="sxs-lookup"><span data-stu-id="07df0-138">Value</span></span>  |<span data-ttu-id="07df0-139">説明</span><span class="sxs-lookup"><span data-stu-id="07df0-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="07df0-140">0x30</span><span class="sxs-lookup"><span data-stu-id="07df0-140">0x30</span></span> | <span data-ttu-id="07df0-141">システムのプロパティのみを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="07df0-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="07df0-142">0x40</span><span class="sxs-lookup"><span data-stu-id="07df0-142">0x40</span></span> | <span data-ttu-id="07df0-143">ローカルおよび伝達されたプロパティが含まれますが、列挙体からシステムのプロパティを除外します。</span><span class="sxs-lookup"><span data-stu-id="07df0-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="07df0-144">クラス。</span><span class="sxs-lookup"><span data-stu-id="07df0-144">For classes:</span></span>

<span data-ttu-id="07df0-145">定数</span><span class="sxs-lookup"><span data-stu-id="07df0-145">Constant</span></span>  |<span data-ttu-id="07df0-146">値</span><span class="sxs-lookup"><span data-stu-id="07df0-146">Value</span></span>  |<span data-ttu-id="07df0-147">説明</span><span class="sxs-lookup"><span data-stu-id="07df0-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="07df0-148">0x100</span><span class="sxs-lookup"><span data-stu-id="07df0-148">0x100</span></span> | <span data-ttu-id="07df0-149">クラスの定義でオーバーライドされたプロパティ、列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="07df0-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="07df0-150">0x100</span><span class="sxs-lookup"><span data-stu-id="07df0-150">0x100</span></span> | <span data-ttu-id="07df0-151">現在のクラス定義でオーバーライドされたプロパティ、およびクラスで定義されている新しいプロパティに列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="07df0-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="07df0-152">0x300</span><span class="sxs-lookup"><span data-stu-id="07df0-152">0x300</span></span> | <span data-ttu-id="07df0-153">A がに対して適用するマスク (フラグ) ではなく、`lEnumFlags`いずれかを確認する値`WBEM_FLAG_CLASS_OVERRIDES_ONLY`または`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`設定されています。</span><span class="sxs-lookup"><span data-stu-id="07df0-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="07df0-154">0x10</span><span class="sxs-lookup"><span data-stu-id="07df0-154">0x10</span></span> | <span data-ttu-id="07df0-155">定義またはクラス自身で変更されるプロパティ、列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="07df0-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="07df0-156">0x20</span><span class="sxs-lookup"><span data-stu-id="07df0-156">0x20</span></span> | <span data-ttu-id="07df0-157">基本クラスから継承されたプロパティ、列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="07df0-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="07df0-158">インスタンス。</span><span class="sxs-lookup"><span data-stu-id="07df0-158">For instances:</span></span>

<span data-ttu-id="07df0-159">定数</span><span class="sxs-lookup"><span data-stu-id="07df0-159">Constant</span></span>  |<span data-ttu-id="07df0-160">値</span><span class="sxs-lookup"><span data-stu-id="07df0-160">Value</span></span>  |<span data-ttu-id="07df0-161">説明</span><span class="sxs-lookup"><span data-stu-id="07df0-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="07df0-162">0x10</span><span class="sxs-lookup"><span data-stu-id="07df0-162">0x10</span></span> | <span data-ttu-id="07df0-163">定義またはクラス自身で変更されるプロパティ、列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="07df0-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="07df0-164">0x20</span><span class="sxs-lookup"><span data-stu-id="07df0-164">0x20</span></span> | <span data-ttu-id="07df0-165">基本クラスから継承されたプロパティ、列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="07df0-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |


## <a name="requirements"></a><span data-ttu-id="07df0-166">要件</span><span class="sxs-lookup"><span data-stu-id="07df0-166">Requirements</span></span>  
 <span data-ttu-id="07df0-167">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="07df0-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07df0-168">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="07df0-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="07df0-169">**.NET framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="07df0-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07df0-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="07df0-170">See also</span></span>  
[<span data-ttu-id="07df0-171">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="07df0-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)