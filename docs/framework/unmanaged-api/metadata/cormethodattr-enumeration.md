---
title: "CorMethodAttr 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodAttr
helpviewer_keywords: CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91afbc9894826b1f44d84f23b550a81d610e3de9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="48ff1-102">CorMethodAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="48ff1-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="48ff1-103">メソッドの機能を記述する値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48ff1-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ff1-104">構文</span><span class="sxs-lookup"><span data-stu-id="48ff1-104">Syntax</span></span>  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="48ff1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="48ff1-105">Members</span></span>  
  
|<span data-ttu-id="48ff1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="48ff1-106">Member</span></span>|<span data-ttu-id="48ff1-107">説明</span><span class="sxs-lookup"><span data-stu-id="48ff1-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="48ff1-108">メンバーへのアクセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="48ff1-109">メンバーを参照できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="48ff1-110">メンバーが、親の型によってのみアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="48ff1-111">メンバーにのみこのアセンブリのサブタイプでアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="48ff1-112">アセンブリ内の誰でもアクセスできます。 のメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="48ff1-113">メンバーに型とサブタイプによってのみアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="48ff1-114">メンバーがそのアセンブリ内の他の型と派生クラスによってアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="48ff1-115">メンバーがスコープにアクセス権を持つすべての型にアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="48ff1-116">インスタンスのメンバーではなく、型の一部として、メンバーが定義されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="48ff1-117">メソッドをオーバーライドできないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="48ff1-118">メソッドをオーバーライドできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="48ff1-119">メソッドには、名前だけではなく、名前とシグネチャで非表示にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="48ff1-120">仮想テーブル レイアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="48ff1-121">仮想テーブルでは、このメソッドの使用、スロットが再利用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="48ff1-122">既定値です。</span><span class="sxs-lookup"><span data-stu-id="48ff1-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="48ff1-123">メソッドは、仮想テーブルの新しいスロットを常に取得を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="48ff1-124">表示は同じ型でメソッドをオーバーライドできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="48ff1-125">メソッドが実装されないように指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="48ff1-126">メソッドが、特別なであると、その名前が記述されているを指定する方法です。</span><span class="sxs-lookup"><span data-stu-id="48ff1-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="48ff1-127">PInvoke を使用して、メソッドの実装が転送されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="48ff1-128">メソッドがアンマネージ コードにエクスポートするマネージ メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="48ff1-129">共通言語ランタイムでは、内部使用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="48ff1-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="48ff1-130">共通言語ランタイムがメソッド名のエンコードを確認する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="48ff1-131">メソッドに関連付けられているセキュリティを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="48ff1-132">メソッドがセキュリティ コードを含む他のメソッドを呼び出すことを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ff1-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48ff1-133">要件</span><span class="sxs-lookup"><span data-stu-id="48ff1-133">Requirements</span></span>  
 <span data-ttu-id="48ff1-134">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="48ff1-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ff1-135">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="48ff1-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="48ff1-136">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ff1-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ff1-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="48ff1-137">See Also</span></span>  
 [<span data-ttu-id="48ff1-138">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="48ff1-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)