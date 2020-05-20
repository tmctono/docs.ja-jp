---
title: CALL_ID 構造体
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 1c795ee536483a7def9c0339efae66a013898a77
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420631"
---
# <a name="call_id-structure"></a><span data-ttu-id="703cb-102">CALL_ID 構造体</span><span class="sxs-lookup"><span data-stu-id="703cb-102">CALL_ID Structure</span></span>
<span data-ttu-id="703cb-103">呼び出されている関数についての情報をデバッガーに提供します。</span><span class="sxs-lookup"><span data-stu-id="703cb-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="703cb-104">詳細については、 [INotifySink2](inotifysink2-interface.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="703cb-104">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="703cb-105">構文</span><span class="sxs-lookup"><span data-stu-id="703cb-105">Syntax</span></span>  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="703cb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="703cb-106">Members</span></span>  
  
|<span data-ttu-id="703cb-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="703cb-107">Member</span></span>|<span data-ttu-id="703cb-108">説明</span><span class="sxs-lookup"><span data-stu-id="703cb-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="703cb-109">呼び出しを行っているコンピューターを識別します。</span><span class="sxs-lookup"><span data-stu-id="703cb-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="703cb-110">マシンプロセッサを識別します。</span><span class="sxs-lookup"><span data-stu-id="703cb-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="703cb-111">呼び出しを実行しているスレッドを識別します。</span><span class="sxs-lookup"><span data-stu-id="703cb-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="703cb-112">呼び出し履歴のアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="703cb-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="703cb-113">呼び出しのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="703cb-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="703cb-114">呼び出しを実行するコンピューターを識別します。</span><span class="sxs-lookup"><span data-stu-id="703cb-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="703cb-115">要件</span><span class="sxs-lookup"><span data-stu-id="703cb-115">Requirements</span></span>  
 <span data-ttu-id="703cb-116">**ヘッダー:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="703cb-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703cb-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="703cb-117">See also</span></span>

- [<span data-ttu-id="703cb-118">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="703cb-118">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="703cb-119">シンボル ストア診断構造体</span><span class="sxs-lookup"><span data-stu-id="703cb-119">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
