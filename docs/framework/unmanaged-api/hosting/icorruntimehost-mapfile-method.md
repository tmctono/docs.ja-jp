---
title: ICorRuntimeHost::MapFile メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
ms.openlocfilehash: 3b1a0cd9a1dfba6f33a20416f2a10c967f871a06
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762670"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="a6b8b-102">ICorRuntimeHost::MapFile メソッド</span><span class="sxs-lookup"><span data-stu-id="a6b8b-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="a6b8b-103">指定されたファイルをメモリにマップします。</span><span class="sxs-lookup"><span data-stu-id="a6b8b-103">Maps the specified file into memory.</span></span> <span data-ttu-id="a6b8b-104">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="a6b8b-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6b8b-105">構文</span><span class="sxs-lookup"><span data-stu-id="a6b8b-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6b8b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6b8b-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="a6b8b-107">からマップするファイルのハンドル。</span><span class="sxs-lookup"><span data-stu-id="a6b8b-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="a6b8b-108">入出力ファイルのマッピングを開始する開始メモリアドレス。</span><span class="sxs-lookup"><span data-stu-id="a6b8b-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6b8b-109">要件</span><span class="sxs-lookup"><span data-stu-id="a6b8b-109">Requirements</span></span>  
 <span data-ttu-id="a6b8b-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6b8b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6b8b-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a6b8b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6b8b-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a6b8b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6b8b-113">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="a6b8b-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b8b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6b8b-114">See also</span></span>

- [<span data-ttu-id="a6b8b-115">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6b8b-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
