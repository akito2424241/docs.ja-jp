---
title: "方法: 相互運用機能アセンブリをタイプ ライブラリから生成する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b8aa6bcd8817b1f432de5d54f596136f4b01bc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>方法: 相互運用機能アセンブリをタイプ ライブラリから生成する
[タイプ ライブラリ インポーター (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) は、COM タイプ ライブラリに含まれているコクラスとインターフェイスをメタデータに変換するコマンド ライン ツールです。 このツールは、型情報の相互運用機能アセンブリと名前空間を自動的に作成します。 クラスのメタデータが使用可能になった後、マネージ クライアントは COM 型のインスタンスを作成し、.NET インスタンスの場合と同じように、そのメソッドを呼び出すことができます。 Tlbimp.exe は、タイプ ライブラリ全体を一度にメタデータに変換しますが、タイプ ライブラリで定義されている型のサブセットの型情報は生成できません。  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>タイプ ライブラリから相互運用機能アセンブリを生成するには  
  
1.  次のコマンドを使用します。  
  
     **tlbimp** \<*type-library-file*>  
  
     **/out:** スイッチを追加することによって、LOANLib.dll などの別の名前で相互運用機能アセンブリを生成します。 相互運用機能アセンブリの名前を変更しておくと、元の COM DLL との区別が付きやすくなり、名前の重複によって発生する可能性のある問題を防ぐことができます。  
  
## <a name="example"></a>例  
 次のコマンドでは、`Loanlib` 名前空間で Loanlib.dll アセンブリを生成します。  
  
```  
tlbimp Loanlib.dll  
```  
  
 次のコマンドでは、別の名前 (LOANLib.dll) で相互運用機能アセンブリが生成されます。  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>参照  
 [タイプ ライブラリのアセンブリとしてのインポート](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [.NET Framework への COM コンポーネントの公開](../../../docs/framework/interop/exposing-com-components.md)
