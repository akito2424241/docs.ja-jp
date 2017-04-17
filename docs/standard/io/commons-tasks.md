---
title: "共通 I/O タスク | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "I/O, 一般的なタスク"
ms.assetid: bf00c380-706a-4e38-b829-454a480629fc
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
---
# 共通 I/O タスク
<xref:System.IO> 名前空間には、読み取り、書き込みなどの各種アクションをファイル、ディレクトリ、およびストリーム上で実行できるようにするいくつかのクラスが用意されています。  詳細については、「[ファイルおよびストリーム入出力](../../../docs/standard/io/index.md)」を参照してください。  
  
## 共通ファイル タスク  
  
|目的|参照項目|  
|--------|----------|  
|テキスト ファイルの作成|<xref:System.IO.File.CreateText%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.FileInfo.CreateText%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.File.Create%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.FileInfo.Create%2A?displayProperty=fullName> メソッド|  
|テキスト ファイルへの書き込み|[方法 : ファイルにテキストを書き込む](../../../docs/standard/io/how-to-write-text-to-a-file.md)<br /><br /> [方法: テキスト ファイルを記述する](../Topic/How%20to:%20Write%20a%20Text%20File%20\(C++-CLI\).md)|  
|テキスト ファイルからの読み取り|[方法 : ファイルからテキストを読み取る](../../../docs/standard/io/how-to-read-text-from-a-file.md)|  
|ファイルへのテキストの追加|[方法 : ログ ファイルを開いて情報を追加する](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)<br /><br /> <xref:System.IO.File.AppendText%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.FileInfo.AppendText%2A?displayProperty=fullName> メソッド|  
|ファイル名の変更またはファイルの移動|<xref:System.IO.File.Move%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.FileInfo.MoveTo%2A?displayProperty=fullName> メソッド|  
|ファイルの削除|<xref:System.IO.File.Delete%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.FileInfo.Delete%2A?displayProperty=fullName> メソッド|  
|ファイルのコピー|<xref:System.IO.File.Copy%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.FileInfo.CopyTo%2A?displayProperty=fullName> メソッド|  
|ファイルのサイズの取得|<xref:System.IO.FileInfo.Length%2A?displayProperty=fullName> プロパティ|  
|ファイルの属性の取得|<xref:System.IO.File.GetAttributes%2A?displayProperty=fullName> メソッド|  
|ファイルの属性の設定|<xref:System.IO.File.SetAttributes%2A?displayProperty=fullName> メソッド|  
|ファイルが存在するかどうかの確認|<xref:System.IO.File.Exists%2A?displayProperty=fullName> メソッド|  
|バイナリ ファイルからの読み取り|[方法 : 新しく作成されたデータ ファイルに対して読み書きする](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|バイナリ ファイルへの書き込み|[方法 : 新しく作成されたデータ ファイルに対して読み書きする](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|ファイル名拡張子の取得|<xref:System.IO.Path.GetExtension%2A?displayProperty=fullName> メソッド|  
|ファイルの絶対パスの取得|<xref:System.IO.Path.GetFullPath%2A?displayProperty=fullName> メソッド|  
|パスからのファイル名と拡張子の取得|<xref:System.IO.Path.GetFileName%2A?displayProperty=fullName> メソッド|  
|ファイルの拡張子の変更|<xref:System.IO.Path.ChangeExtension%2A?displayProperty=fullName> メソッド|  
  
## 共通ディレクトリ タスク  
  
|目的|参照項目|  
|--------|----------|  
|My Documents などの特別なフォルダー内のファイルへのアクセス|[方法 : ファイルにテキストを書き込む](../../../docs/standard/io/how-to-write-text-to-a-file.md)|  
|ディレクトリの作成|<xref:System.IO.Directory.CreateDirectory%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.FileInfo.Directory%2A?displayProperty=fullName> プロパティ|  
|サブディレクトリの作成|<xref:System.IO.DirectoryInfo.CreateSubdirectory%2A?displayProperty=fullName> メソッド|  
|ディレクトリ名の変更またはディレクトリの移動|<xref:System.IO.Directory.Move%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.DirectoryInfo.MoveTo%2A?displayProperty=fullName> メソッド|  
|ディレクトリのコピー|[方法 : ディレクトリをコピーする](../../../docs/standard/io/how-to-copy-directories.md)|  
|ディレクトリの削除|<xref:System.IO.Directory.Delete%2A?displayProperty=fullName> メソッド<br /><br /> <xref:System.IO.DirectoryInfo.Delete%2A?displayProperty=fullName> メソッド|  
|ディレクトリ内のファイルとサブディレクトリの確認|[方法: ディレクトリとファイルを列挙する](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)|  
|ディレクトリのサイズの確認|<xref:System.IO.Directory?displayProperty=fullName> クラス|  
|ディレクトリが存在するかどうかの確認|<xref:System.IO.Directory.Exists%2A?displayProperty=fullName> メソッド|  
  
## 参照  
 [ファイルおよびストリーム入出力](../../../docs/standard/io/index.md)   
 [ストリームの構成](../../../docs/standard/io/composing-streams.md)   
 [非同期ファイル I\/O](../../../docs/standard/io/非同期ファイル-i-o.md)