---
title: エラー - Transact-SQL の実行は、デバッグされないで終了しました | Microsoft Docs
ms.date: 11/08/2018
ms.topic: error-reference
f1_keywords:
- vs.debug.error.sqlde_sql_executed_but_not_debugged
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e141fac7fba1939811c722d8e08f49531111ff7e
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2020
ms.locfileid: "85460248"
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>エラー :Transact-SQL の実行は、デバッグされないで終了しました

このエラーは、Transact-SQL プロシージャまたは SQLCLR プロシージャをデバッグしようとしたときに、デバッガーが SQL Server からデバッグ メッセージを受信しなかった場合に発生します。

この問題は、ネットワークの問題や SQL Server の問題によって発生することもありますが、最も可能性が高いのはアクセス許可の問題です。

このエラーには、次の 2 つのアカウントが関係します。

- アプリケーション アカウントは、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] を実行しているユーザー アカウントです。

- 接続アカウントは、SQL Server に接続するために使用される ID です。 接続が SQL 認証を使用している場合、このアカウントは Visual Studio が実行されている ID と同じであるとは限りません。

  SQL デバッグでは、アプリケーション アカウントが接続アカウントと一致しているか、または sysadmin である必要があります。

  sa などの SQL アカウント名を使用している場合は、アプリケーション アカウントが sysadmin として SQL Server 上でセットアップされている必要があります。 既定では、SQL サーバーが実行されているコンピューターの管理者は SQL Server の sysadmin です。

  このエラーを解決するには、次の手順を行う必要があります。

  - アクセス許可の設定を確認します。 詳細については、「[方法:デバッグ用の SQL Server の権限の設定](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)に関するページを参照してください。

  - SQL デバッグが正しく設定されていることを確認します。

  - ネットワーク管理者またはデータベース管理者に問い合わせます。

## <a name="see-also"></a>関連項目

- [SQL デバッグの設定](/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100))
- [方法: デバッグ用の SQL Server の権限を設定する](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)
- [デバッガーの設定と準備](../debugger/debugger-settings-and-preparation.md)
- [Remote Debugging](../debugger/remote-debugging.md)