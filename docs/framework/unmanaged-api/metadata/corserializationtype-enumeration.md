---
title: "CorSerializationType 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSerializationType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSerializationType
helpviewer_keywords: CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f6650298364f7deb60d553ee21f5028f5cbe7400
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="25b59-102">CorSerializationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="25b59-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="25b59-103">共通言語ランタイムによってオブジェクトをシリアル化する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="25b59-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b59-104">構文</span><span class="sxs-lookup"><span data-stu-id="25b59-104">Syntax</span></span>  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="25b59-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="25b59-105">Members</span></span>  
  
|<span data-ttu-id="25b59-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="25b59-106">Member</span></span>|<span data-ttu-id="25b59-107">説明</span><span class="sxs-lookup"><span data-stu-id="25b59-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="25b59-108">オブジェクトのシリアル化が定義されていません。</span><span class="sxs-lookup"><span data-stu-id="25b59-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="25b59-109">ブール型としてオブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="25b59-110">オブジェクトは、文字型としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="25b59-111">オブジェクトは、1 バイトの符号付き整数としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="25b59-112">オブジェクトは 1 バイトの符号なし整数としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="25b59-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="25b59-113">オブジェクトは、2 バイトの符号付き整数としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="25b59-114">オブジェクトは 2 バイトの符号なし整数としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="25b59-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="25b59-115">オブジェクトは、4 バイトの符号付き整数としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="25b59-116">オブジェクトは、4 バイトの符号なし整数としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="25b59-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="25b59-117">オブジェクトは、8 バイトの符号付き整数としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="25b59-118">オブジェクトは 8 バイトの符号なし整数としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="25b59-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="25b59-119">オブジェクトは、4 バイト浮動小数点としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="25b59-120">オブジェクトは、8 バイト浮動小数点としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="25b59-121">オブジェクトは、System.String 型としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="25b59-122">オブジェクトは、1 次元、としてシリアル化 0 下限値の配列。</span><span class="sxs-lookup"><span data-stu-id="25b59-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="25b59-123">オブジェクトは、ジェネリック型としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="25b59-124">オブジェクトは、タグが付けられたオブジェクトとしてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="25b59-125">オブジェクトは、フィールドとしてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="25b59-126">オブジェクトのプロパティとしてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="25b59-127">オブジェクトの列挙体としてシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="25b59-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25b59-128">要件</span><span class="sxs-lookup"><span data-stu-id="25b59-128">Requirements</span></span>  
 <span data-ttu-id="25b59-129">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="25b59-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25b59-130">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="25b59-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="25b59-131">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25b59-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b59-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="25b59-132">See Also</span></span>  
 [<span data-ttu-id="25b59-133">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="25b59-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)