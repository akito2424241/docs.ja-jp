---
title: "方法 : Visual Basic で特定のパターンを持つファイルをディレクトリにコピーする"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ead158a95d7f3ef4d0cd650b3b1a1db7042ccb29
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a>方法 : Visual Basic で特定のパターンを持つファイルをディレクトリにコピーする
<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> メソッドは、ファイルのパス名を表す文字列の読み取り専用のコレクションを返します。 `wildCards` パラメーターを使用して、特定のパターンを指定できます。  
  
 一致するファイルが見つからない場合は、空のコレクションが返されます。  
  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> メソッドを使用して、ファイルをディレクトリにコピーできます。  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a>特定のパターンを持つファイルをディレクトリにコピーするには  
  
1.  `GetFiles` メソッドを使用して、ファイルの一覧を返します。 この例は、指定したディレクトリ内のすべての .rtf ファイルを返します。  
  
     [!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]  
  
2.  `CopyFile` メソッドを使用して、ファイルをコピーします。 この例では、 `testdirectory`という名前のディレクトリにファイルをコピーします。  
  
     [!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]  
  
3.  `For` ステートメントを `Next` ステートメントで閉じます。  
  
     [!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]  
  
## <a name="example"></a>例  
 次の例は、上記のスニペットを完全な形で示したもので、指定したディレクトリのすべての .rtf ファイルを `testdirectory`という名前のディレクトリにコピーします。  
  
 [!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 次の条件を満たす場合は、例外が発生する可能性があります。  
  
-   パスが正しくない。長さが 0 の文字列である、空白だけが含まれている、使用できない文字が含まれている、デバイス パスである (先頭が \\\\.\\)、のいずれかの理由が考えられる (<xref:System.ArgumentException>)。  
  
-   パスが `Nothing` であるため、有効でない (<xref:System.ArgumentNullException>)  
  
-   ディレクトリが存在しない (<xref:System.IO.DirectoryNotFoundException>)。  
  
-   ディレクトリが既存のファイルを指している (<xref:System.IO.IOException>)。  
  
-   パスがシステムで定義されている最大長を超えている (<xref:System.IO.PathTooLongException>)。  
  
-   パス内のファイル名またはディレクトリ名にコロン (:) が含まれているか、または形式が無効である (<xref:System.NotSupportedException>)  
  
-   ユーザーがパスを参照するのに必要なアクセス許可がない (<xref:System.Security.SecurityException>) ユーザーに必要な権限がない (<xref:System.UnauthorizedAccessException>)。  
  
## <a name="see-also"></a>関連項目  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>  
 [方法: 特定のパターンに一致するサブディレクトリを検索する](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)  
 [トラブルシューティング : テキスト ファイルの読み取りと書き込み](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 [方法: ディレクトリにあるファイルのコレクションを取得する](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
