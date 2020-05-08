---
title: OLE DB スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783450"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="fee37-102">OLE DB スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="fee37-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="fee37-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 OLE DB プロバイダーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fee37-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="fee37-104">Microsoft SQL Server OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="fee37-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="fee37-105">Microsoft SQL Server OLE DB Driver では、共通のスキーマ コレクションに加えて、次の特定のスキーマ コレクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fee37-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="fee37-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="fee37-106">Tables</span></span>  
  
- <span data-ttu-id="fee37-107">列</span><span class="sxs-lookup"><span data-stu-id="fee37-107">Columns</span></span>  
  
- <span data-ttu-id="fee37-108">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fee37-108">Procedures</span></span>  
  
- <span data-ttu-id="fee37-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fee37-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="fee37-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="fee37-110">Catalog</span></span>  
  
- <span data-ttu-id="fee37-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="fee37-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="fee37-112">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="fee37-112">Tables</span></span>  
  
|<span data-ttu-id="fee37-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-113">ColumnName</span></span>|<span data-ttu-id="fee37-114">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-115">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-116">String</span><span class="sxs-lookup"><span data-stu-id="fee37-116">String</span></span>|  
|<span data-ttu-id="fee37-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-118">String</span><span class="sxs-lookup"><span data-stu-id="fee37-118">String</span></span>|  
|<span data-ttu-id="fee37-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-119">TABLE_NAME</span></span>|<span data-ttu-id="fee37-120">String</span><span class="sxs-lookup"><span data-stu-id="fee37-120">String</span></span>|  
|<span data-ttu-id="fee37-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-121">TABLE_TYPE</span></span>|<span data-ttu-id="fee37-122">String</span><span class="sxs-lookup"><span data-stu-id="fee37-122">String</span></span>|  
|<span data-ttu-id="fee37-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-123">TABLE_GUID</span></span>|<span data-ttu-id="fee37-124">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-124">Guid</span></span>|  
|<span data-ttu-id="fee37-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-125">DESCRIPTION</span></span>|<span data-ttu-id="fee37-126">String</span><span class="sxs-lookup"><span data-stu-id="fee37-126">String</span></span>|  
|<span data-ttu-id="fee37-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-127">TABLE_PROPID</span></span>|<span data-ttu-id="fee37-128">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-128">Int64</span></span>|  
|<span data-ttu-id="fee37-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fee37-129">DATE_CREATED</span></span>|<span data-ttu-id="fee37-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-130">DateTime</span></span>|  
|<span data-ttu-id="fee37-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fee37-131">DATE_MODIFIED</span></span>|<span data-ttu-id="fee37-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fee37-133">列</span><span class="sxs-lookup"><span data-stu-id="fee37-133">Columns</span></span>  
  
|<span data-ttu-id="fee37-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-134">ColumnName</span></span>|<span data-ttu-id="fee37-135">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-136">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-137">String</span><span class="sxs-lookup"><span data-stu-id="fee37-137">String</span></span>|  
|<span data-ttu-id="fee37-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-139">String</span><span class="sxs-lookup"><span data-stu-id="fee37-139">String</span></span>|  
|<span data-ttu-id="fee37-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-140">TABLE_NAME</span></span>|<span data-ttu-id="fee37-141">String</span><span class="sxs-lookup"><span data-stu-id="fee37-141">String</span></span>|  
|<span data-ttu-id="fee37-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-142">COLUMN_NAME</span></span>|<span data-ttu-id="fee37-143">String</span><span class="sxs-lookup"><span data-stu-id="fee37-143">String</span></span>|  
|<span data-ttu-id="fee37-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-144">COLUMN_GUID</span></span>|<span data-ttu-id="fee37-145">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-145">Guid</span></span>|  
|<span data-ttu-id="fee37-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-146">COLUMN_PROPID</span></span>|<span data-ttu-id="fee37-147">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-147">Int64</span></span>|  
|<span data-ttu-id="fee37-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fee37-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="fee37-149">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-149">Int64</span></span>|  
|<span data-ttu-id="fee37-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="fee37-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="fee37-151">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-151">Boolean</span></span>|  
|<span data-ttu-id="fee37-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fee37-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="fee37-153">String</span><span class="sxs-lookup"><span data-stu-id="fee37-153">String</span></span>|  
|<span data-ttu-id="fee37-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fee37-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="fee37-155">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-155">Int64</span></span>|  
|<span data-ttu-id="fee37-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fee37-156">IS_NULLABLE</span></span>|<span data-ttu-id="fee37-157">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-157">Boolean</span></span>|  
|<span data-ttu-id="fee37-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-158">DATA_TYPE</span></span>|<span data-ttu-id="fee37-159">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-159">Int32</span></span>|  
|<span data-ttu-id="fee37-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-160">TYPE_GUID</span></span>|<span data-ttu-id="fee37-161">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-161">Guid</span></span>|  
|<span data-ttu-id="fee37-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fee37-163">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-163">Int64</span></span>|  
|<span data-ttu-id="fee37-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fee37-165">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-165">Int64</span></span>|  
|<span data-ttu-id="fee37-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fee37-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fee37-167">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-167">Int32</span></span>|  
|<span data-ttu-id="fee37-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fee37-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="fee37-169">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-169">Int16</span></span>|  
|<span data-ttu-id="fee37-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fee37-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="fee37-171">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-171">Int64</span></span>|  
|<span data-ttu-id="fee37-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="fee37-173">String</span><span class="sxs-lookup"><span data-stu-id="fee37-173">String</span></span>|  
|<span data-ttu-id="fee37-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="fee37-175">String</span><span class="sxs-lookup"><span data-stu-id="fee37-175">String</span></span>|  
|<span data-ttu-id="fee37-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="fee37-177">String</span><span class="sxs-lookup"><span data-stu-id="fee37-177">String</span></span>|  
|<span data-ttu-id="fee37-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="fee37-179">String</span><span class="sxs-lookup"><span data-stu-id="fee37-179">String</span></span>|  
|<span data-ttu-id="fee37-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="fee37-181">String</span><span class="sxs-lookup"><span data-stu-id="fee37-181">String</span></span>|  
|<span data-ttu-id="fee37-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-182">COLLATION_NAME</span></span>|<span data-ttu-id="fee37-183">String</span><span class="sxs-lookup"><span data-stu-id="fee37-183">String</span></span>|  
|<span data-ttu-id="fee37-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="fee37-185">String</span><span class="sxs-lookup"><span data-stu-id="fee37-185">String</span></span>|  
|<span data-ttu-id="fee37-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="fee37-187">String</span><span class="sxs-lookup"><span data-stu-id="fee37-187">String</span></span>|  
|<span data-ttu-id="fee37-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-188">DOMAIN_NAME</span></span>|<span data-ttu-id="fee37-189">String</span><span class="sxs-lookup"><span data-stu-id="fee37-189">String</span></span>|  
|<span data-ttu-id="fee37-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-190">DESCRIPTION</span></span>|<span data-ttu-id="fee37-191">String</span><span class="sxs-lookup"><span data-stu-id="fee37-191">String</span></span>|  
|<span data-ttu-id="fee37-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="fee37-192">COLUMN_LCID</span></span>|<span data-ttu-id="fee37-193">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-193">Int32</span></span>|  
|<span data-ttu-id="fee37-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="fee37-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="fee37-195">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-195">Int32</span></span>|  
|<span data-ttu-id="fee37-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="fee37-196">COLUMN_SORTID</span></span>|<span data-ttu-id="fee37-197">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-197">Int32</span></span>|  
|<span data-ttu-id="fee37-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="fee37-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="fee37-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="fee37-199">Byte[]</span></span>|  
|<span data-ttu-id="fee37-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="fee37-200">IS_COMPUTED</span></span>|<span data-ttu-id="fee37-201">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fee37-202">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fee37-202">Procedures</span></span>  
  
|<span data-ttu-id="fee37-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-203">ColumnName</span></span>|<span data-ttu-id="fee37-204">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fee37-206">String</span><span class="sxs-lookup"><span data-stu-id="fee37-206">String</span></span>|  
|<span data-ttu-id="fee37-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fee37-208">String</span><span class="sxs-lookup"><span data-stu-id="fee37-208">String</span></span>|  
|<span data-ttu-id="fee37-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="fee37-210">String</span><span class="sxs-lookup"><span data-stu-id="fee37-210">String</span></span>|  
|<span data-ttu-id="fee37-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fee37-212">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-212">Int16</span></span>|  
|<span data-ttu-id="fee37-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fee37-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="fee37-214">String</span><span class="sxs-lookup"><span data-stu-id="fee37-214">String</span></span>|  
|<span data-ttu-id="fee37-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-215">DESCRIPTION</span></span>|<span data-ttu-id="fee37-216">String</span><span class="sxs-lookup"><span data-stu-id="fee37-216">String</span></span>|  
|<span data-ttu-id="fee37-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fee37-217">DATE_CREATED</span></span>|<span data-ttu-id="fee37-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-218">DateTime</span></span>|  
|<span data-ttu-id="fee37-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fee37-219">DATE_MODIFIED</span></span>|<span data-ttu-id="fee37-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="fee37-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fee37-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="fee37-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-222">ColumnName</span></span>|<span data-ttu-id="fee37-223">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fee37-225">String</span><span class="sxs-lookup"><span data-stu-id="fee37-225">String</span></span>|  
|<span data-ttu-id="fee37-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fee37-227">String</span><span class="sxs-lookup"><span data-stu-id="fee37-227">String</span></span>|  
|<span data-ttu-id="fee37-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="fee37-229">String</span><span class="sxs-lookup"><span data-stu-id="fee37-229">String</span></span>|  
|<span data-ttu-id="fee37-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-230">PARAMETER_NAME</span></span>|<span data-ttu-id="fee37-231">String</span><span class="sxs-lookup"><span data-stu-id="fee37-231">String</span></span>|  
|<span data-ttu-id="fee37-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fee37-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="fee37-233">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-233">Int32</span></span>|  
|<span data-ttu-id="fee37-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="fee37-235">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-235">Int32</span></span>|  
|<span data-ttu-id="fee37-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="fee37-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="fee37-237">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-237">Boolean</span></span>|  
|<span data-ttu-id="fee37-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fee37-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="fee37-239">String</span><span class="sxs-lookup"><span data-stu-id="fee37-239">String</span></span>|  
|<span data-ttu-id="fee37-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fee37-240">IS_NULLABLE</span></span>|<span data-ttu-id="fee37-241">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-241">Boolean</span></span>|  
|<span data-ttu-id="fee37-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-242">DATA_TYPE</span></span>|<span data-ttu-id="fee37-243">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-243">Int32</span></span>|  
|<span data-ttu-id="fee37-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fee37-245">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-245">Int64</span></span>|  
|<span data-ttu-id="fee37-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fee37-247">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-247">Int64</span></span>|  
|<span data-ttu-id="fee37-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fee37-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fee37-249">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-249">Int32</span></span>|  
|<span data-ttu-id="fee37-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fee37-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="fee37-251">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-251">Int16</span></span>|  
|<span data-ttu-id="fee37-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-252">DESCRIPTION</span></span>|<span data-ttu-id="fee37-253">String</span><span class="sxs-lookup"><span data-stu-id="fee37-253">String</span></span>|  
|<span data-ttu-id="fee37-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-254">TYPE_NAME</span></span>|<span data-ttu-id="fee37-255">String</span><span class="sxs-lookup"><span data-stu-id="fee37-255">String</span></span>|  
|<span data-ttu-id="fee37-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="fee37-257">String</span><span class="sxs-lookup"><span data-stu-id="fee37-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="fee37-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="fee37-258">Catalog</span></span>  
  
|<span data-ttu-id="fee37-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-259">ColumnName</span></span>|<span data-ttu-id="fee37-260">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-261">CATALOG_NAME</span></span>|<span data-ttu-id="fee37-262">String</span><span class="sxs-lookup"><span data-stu-id="fee37-262">String</span></span>|  
|<span data-ttu-id="fee37-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-263">DESCRIPTION</span></span>|<span data-ttu-id="fee37-264">String</span><span class="sxs-lookup"><span data-stu-id="fee37-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="fee37-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="fee37-265">Indexes</span></span>  
  
|<span data-ttu-id="fee37-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-266">ColumnName</span></span>|<span data-ttu-id="fee37-267">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-268">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-269">String</span><span class="sxs-lookup"><span data-stu-id="fee37-269">String</span></span>|  
|<span data-ttu-id="fee37-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-271">String</span><span class="sxs-lookup"><span data-stu-id="fee37-271">String</span></span>|  
|<span data-ttu-id="fee37-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-272">TABLE_NAME</span></span>|<span data-ttu-id="fee37-273">String</span><span class="sxs-lookup"><span data-stu-id="fee37-273">String</span></span>|  
|<span data-ttu-id="fee37-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-274">INDEX_CATALOG</span></span>|<span data-ttu-id="fee37-275">String</span><span class="sxs-lookup"><span data-stu-id="fee37-275">String</span></span>|  
|<span data-ttu-id="fee37-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="fee37-277">String</span><span class="sxs-lookup"><span data-stu-id="fee37-277">String</span></span>|  
|<span data-ttu-id="fee37-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-278">INDEX_NAME</span></span>|<span data-ttu-id="fee37-279">String</span><span class="sxs-lookup"><span data-stu-id="fee37-279">String</span></span>|  
|<span data-ttu-id="fee37-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="fee37-280">PRIMARY_KEY</span></span>|<span data-ttu-id="fee37-281">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-281">Boolean</span></span>|  
|<span data-ttu-id="fee37-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="fee37-282">UNIQUE</span></span>|<span data-ttu-id="fee37-283">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-283">Boolean</span></span>|  
|<span data-ttu-id="fee37-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="fee37-284">CLUSTERED</span></span>|<span data-ttu-id="fee37-285">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-285">Boolean</span></span>|  
|<span data-ttu-id="fee37-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-286">TYPE</span></span>|<span data-ttu-id="fee37-287">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-287">Int32</span></span>|  
|<span data-ttu-id="fee37-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="fee37-288">FILL_FACTOR</span></span>|<span data-ttu-id="fee37-289">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-289">Int32</span></span>|  
|<span data-ttu-id="fee37-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="fee37-290">INITIAL_SIZE</span></span>|<span data-ttu-id="fee37-291">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-291">Int32</span></span>|  
|<span data-ttu-id="fee37-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="fee37-292">NULLS</span></span>|<span data-ttu-id="fee37-293">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-293">Int32</span></span>|  
|<span data-ttu-id="fee37-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="fee37-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="fee37-295">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-295">Boolean</span></span>|  
|<span data-ttu-id="fee37-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="fee37-296">AUTO_UPDATE</span></span>|<span data-ttu-id="fee37-297">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-297">Boolean</span></span>|  
|<span data-ttu-id="fee37-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="fee37-298">NULL_COLLATION</span></span>|<span data-ttu-id="fee37-299">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-299">Int32</span></span>|  
|<span data-ttu-id="fee37-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fee37-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="fee37-301">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-301">Int64</span></span>|  
|<span data-ttu-id="fee37-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-302">COLUMN_NAME</span></span>|<span data-ttu-id="fee37-303">String</span><span class="sxs-lookup"><span data-stu-id="fee37-303">String</span></span>|  
|<span data-ttu-id="fee37-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-304">COLUMN_GUID</span></span>|<span data-ttu-id="fee37-305">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-305">Guid</span></span>|  
|<span data-ttu-id="fee37-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-306">COLUMN_PROPID</span></span>|<span data-ttu-id="fee37-307">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-307">Int64</span></span>|  
|<span data-ttu-id="fee37-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="fee37-308">COLLATION</span></span>|<span data-ttu-id="fee37-309">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-309">Int16</span></span>|  
|<span data-ttu-id="fee37-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="fee37-310">CARDINALITY</span></span>|<span data-ttu-id="fee37-311">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="fee37-311">Decimal</span></span>|  
|<span data-ttu-id="fee37-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="fee37-312">PAGES</span></span>|<span data-ttu-id="fee37-313">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-313">Int32</span></span>|  
|<span data-ttu-id="fee37-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="fee37-314">FILTER_CONDITION</span></span>|<span data-ttu-id="fee37-315">String</span><span class="sxs-lookup"><span data-stu-id="fee37-315">String</span></span>|  
|<span data-ttu-id="fee37-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="fee37-316">INTEGRATED</span></span>|<span data-ttu-id="fee37-317">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="fee37-318">Microsoft Oracle OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="fee37-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="fee37-319">Microsoft Oracle OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fee37-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="fee37-320">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="fee37-320">Tables</span></span>  
  
- <span data-ttu-id="fee37-321">列</span><span class="sxs-lookup"><span data-stu-id="fee37-321">Columns</span></span>  
  
- <span data-ttu-id="fee37-322">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fee37-322">Procedures</span></span>  
  
- <span data-ttu-id="fee37-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fee37-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="fee37-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fee37-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="fee37-325">Views</span><span class="sxs-lookup"><span data-stu-id="fee37-325">Views</span></span>  
  
- <span data-ttu-id="fee37-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="fee37-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="fee37-327">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="fee37-327">Tables</span></span>  
  
|<span data-ttu-id="fee37-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-328">ColumnName</span></span>|<span data-ttu-id="fee37-329">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-330">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-331">String</span><span class="sxs-lookup"><span data-stu-id="fee37-331">String</span></span>|  
|<span data-ttu-id="fee37-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-333">String</span><span class="sxs-lookup"><span data-stu-id="fee37-333">String</span></span>|  
|<span data-ttu-id="fee37-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-334">TABLE_NAME</span></span>|<span data-ttu-id="fee37-335">String</span><span class="sxs-lookup"><span data-stu-id="fee37-335">String</span></span>|  
|<span data-ttu-id="fee37-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-336">TABLE_TYPE</span></span>|<span data-ttu-id="fee37-337">String</span><span class="sxs-lookup"><span data-stu-id="fee37-337">String</span></span>|  
|<span data-ttu-id="fee37-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-338">TABLE_GUID</span></span>|<span data-ttu-id="fee37-339">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-339">Guid</span></span>|  
|<span data-ttu-id="fee37-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-340">DESCRIPTION</span></span>|<span data-ttu-id="fee37-341">String</span><span class="sxs-lookup"><span data-stu-id="fee37-341">String</span></span>|  
|<span data-ttu-id="fee37-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-342">TABLE_PROPID</span></span>|<span data-ttu-id="fee37-343">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-343">Int64</span></span>|  
|<span data-ttu-id="fee37-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fee37-344">DATE_CREATED</span></span>|<span data-ttu-id="fee37-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-345">DateTime</span></span>|  
|<span data-ttu-id="fee37-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fee37-346">DATE_MODIFIED</span></span>|<span data-ttu-id="fee37-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fee37-348">列</span><span class="sxs-lookup"><span data-stu-id="fee37-348">Columns</span></span>  
  
|<span data-ttu-id="fee37-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-349">ColumnName</span></span>|<span data-ttu-id="fee37-350">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-351">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-352">String</span><span class="sxs-lookup"><span data-stu-id="fee37-352">String</span></span>|  
|<span data-ttu-id="fee37-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-354">String</span><span class="sxs-lookup"><span data-stu-id="fee37-354">String</span></span>|  
|<span data-ttu-id="fee37-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-355">TABLE_NAME</span></span>|<span data-ttu-id="fee37-356">String</span><span class="sxs-lookup"><span data-stu-id="fee37-356">String</span></span>|  
|<span data-ttu-id="fee37-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-357">COLUMN_NAME</span></span>|<span data-ttu-id="fee37-358">String</span><span class="sxs-lookup"><span data-stu-id="fee37-358">String</span></span>|  
|<span data-ttu-id="fee37-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-359">COLUMN_GUID</span></span>|<span data-ttu-id="fee37-360">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-360">Guid</span></span>|  
|<span data-ttu-id="fee37-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-361">COLUMN_PROPID</span></span>|<span data-ttu-id="fee37-362">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-362">Int64</span></span>|  
|<span data-ttu-id="fee37-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fee37-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="fee37-364">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-364">Int64</span></span>|  
|<span data-ttu-id="fee37-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="fee37-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="fee37-366">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-366">Boolean</span></span>|  
|<span data-ttu-id="fee37-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fee37-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="fee37-368">String</span><span class="sxs-lookup"><span data-stu-id="fee37-368">String</span></span>|  
|<span data-ttu-id="fee37-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fee37-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="fee37-370">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-370">Int64</span></span>|  
|<span data-ttu-id="fee37-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fee37-371">IS_NULLABLE</span></span>|<span data-ttu-id="fee37-372">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-372">Boolean</span></span>|  
|<span data-ttu-id="fee37-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-373">DATA_TYPE</span></span>|<span data-ttu-id="fee37-374">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-374">Int32</span></span>|  
|<span data-ttu-id="fee37-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-375">TYPE_GUID</span></span>|<span data-ttu-id="fee37-376">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-376">Guid</span></span>|  
|<span data-ttu-id="fee37-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fee37-378">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-378">Int64</span></span>|  
|<span data-ttu-id="fee37-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fee37-380">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-380">Int64</span></span>|  
|<span data-ttu-id="fee37-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fee37-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fee37-382">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-382">Int32</span></span>|  
|<span data-ttu-id="fee37-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fee37-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="fee37-384">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-384">Int16</span></span>|  
|<span data-ttu-id="fee37-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fee37-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="fee37-386">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-386">Int64</span></span>|  
|<span data-ttu-id="fee37-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="fee37-388">String</span><span class="sxs-lookup"><span data-stu-id="fee37-388">String</span></span>|  
|<span data-ttu-id="fee37-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="fee37-390">String</span><span class="sxs-lookup"><span data-stu-id="fee37-390">String</span></span>|  
|<span data-ttu-id="fee37-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="fee37-392">String</span><span class="sxs-lookup"><span data-stu-id="fee37-392">String</span></span>|  
|<span data-ttu-id="fee37-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="fee37-394">String</span><span class="sxs-lookup"><span data-stu-id="fee37-394">String</span></span>|  
|<span data-ttu-id="fee37-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="fee37-396">String</span><span class="sxs-lookup"><span data-stu-id="fee37-396">String</span></span>|  
|<span data-ttu-id="fee37-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-397">COLLATION_NAME</span></span>|<span data-ttu-id="fee37-398">String</span><span class="sxs-lookup"><span data-stu-id="fee37-398">String</span></span>|  
|<span data-ttu-id="fee37-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="fee37-400">String</span><span class="sxs-lookup"><span data-stu-id="fee37-400">String</span></span>|  
|<span data-ttu-id="fee37-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="fee37-402">String</span><span class="sxs-lookup"><span data-stu-id="fee37-402">String</span></span>|  
|<span data-ttu-id="fee37-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-403">DOMAIN_NAME</span></span>|<span data-ttu-id="fee37-404">String</span><span class="sxs-lookup"><span data-stu-id="fee37-404">String</span></span>|  
|<span data-ttu-id="fee37-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-405">DESCRIPTION</span></span>|<span data-ttu-id="fee37-406">String</span><span class="sxs-lookup"><span data-stu-id="fee37-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fee37-407">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fee37-407">Procedures</span></span>  
  
|<span data-ttu-id="fee37-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-408">ColumnName</span></span>|<span data-ttu-id="fee37-409">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fee37-411">String</span><span class="sxs-lookup"><span data-stu-id="fee37-411">String</span></span>|  
|<span data-ttu-id="fee37-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fee37-413">String</span><span class="sxs-lookup"><span data-stu-id="fee37-413">String</span></span>|  
|<span data-ttu-id="fee37-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="fee37-415">String</span><span class="sxs-lookup"><span data-stu-id="fee37-415">String</span></span>|  
|<span data-ttu-id="fee37-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fee37-417">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-417">Int16</span></span>|  
|<span data-ttu-id="fee37-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fee37-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="fee37-419">String</span><span class="sxs-lookup"><span data-stu-id="fee37-419">String</span></span>|  
|<span data-ttu-id="fee37-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-420">DESCRIPTION</span></span>|<span data-ttu-id="fee37-421">String</span><span class="sxs-lookup"><span data-stu-id="fee37-421">String</span></span>|  
|<span data-ttu-id="fee37-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fee37-422">DATE_CREATED</span></span>|<span data-ttu-id="fee37-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-423">DateTime</span></span>|  
|<span data-ttu-id="fee37-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fee37-424">DATE_MODIFIED</span></span>|<span data-ttu-id="fee37-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="fee37-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fee37-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="fee37-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-427">ColumnName</span></span>|<span data-ttu-id="fee37-428">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fee37-430">String</span><span class="sxs-lookup"><span data-stu-id="fee37-430">String</span></span>|  
|<span data-ttu-id="fee37-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fee37-432">String</span><span class="sxs-lookup"><span data-stu-id="fee37-432">String</span></span>|  
|<span data-ttu-id="fee37-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="fee37-434">String</span><span class="sxs-lookup"><span data-stu-id="fee37-434">String</span></span>|  
|<span data-ttu-id="fee37-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-435">COLUMN_NAME</span></span>|<span data-ttu-id="fee37-436">String</span><span class="sxs-lookup"><span data-stu-id="fee37-436">String</span></span>|  
|<span data-ttu-id="fee37-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-437">COLUMN_GUID</span></span>|<span data-ttu-id="fee37-438">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-438">Guid</span></span>|  
|<span data-ttu-id="fee37-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-439">COLUMN_PROPID</span></span>|<span data-ttu-id="fee37-440">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-440">Int64</span></span>|  
|<span data-ttu-id="fee37-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="fee37-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="fee37-442">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-442">Int64</span></span>|  
|<span data-ttu-id="fee37-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fee37-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="fee37-444">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-444">Int64</span></span>|  
|<span data-ttu-id="fee37-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fee37-445">IS_NULLABLE</span></span>|<span data-ttu-id="fee37-446">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-446">Boolean</span></span>|  
|<span data-ttu-id="fee37-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-447">DATA_TYPE</span></span>|<span data-ttu-id="fee37-448">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-448">Int32</span></span>|  
|<span data-ttu-id="fee37-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-449">TYPE_GUID</span></span>|<span data-ttu-id="fee37-450">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-450">Guid</span></span>|  
|<span data-ttu-id="fee37-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fee37-452">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-452">Int64</span></span>|  
|<span data-ttu-id="fee37-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fee37-454">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-454">Int64</span></span>|  
|<span data-ttu-id="fee37-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fee37-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fee37-456">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-456">Int32</span></span>|  
|<span data-ttu-id="fee37-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fee37-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="fee37-458">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-458">Int16</span></span>|  
|<span data-ttu-id="fee37-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-459">DESCRIPTION</span></span>|<span data-ttu-id="fee37-460">String</span><span class="sxs-lookup"><span data-stu-id="fee37-460">String</span></span>|  
|<span data-ttu-id="fee37-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="fee37-461">OVERLOAD</span></span>|<span data-ttu-id="fee37-462">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="fee37-463">Views</span><span class="sxs-lookup"><span data-stu-id="fee37-463">Views</span></span>  
  
|<span data-ttu-id="fee37-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-464">ColumnName</span></span>|<span data-ttu-id="fee37-465">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-466">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-467">String</span><span class="sxs-lookup"><span data-stu-id="fee37-467">String</span></span>|  
|<span data-ttu-id="fee37-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-469">String</span><span class="sxs-lookup"><span data-stu-id="fee37-469">String</span></span>|  
|<span data-ttu-id="fee37-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-470">TABLE_NAME</span></span>|<span data-ttu-id="fee37-471">String</span><span class="sxs-lookup"><span data-stu-id="fee37-471">String</span></span>|  
|<span data-ttu-id="fee37-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fee37-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="fee37-473">String</span><span class="sxs-lookup"><span data-stu-id="fee37-473">String</span></span>|  
|<span data-ttu-id="fee37-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-474">CHECK_OPTION</span></span>|<span data-ttu-id="fee37-475">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-475">Boolean</span></span>|  
|<span data-ttu-id="fee37-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="fee37-476">IS_UPDATABLE</span></span>|<span data-ttu-id="fee37-477">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-477">Boolean</span></span>|  
|<span data-ttu-id="fee37-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-478">DESCRIPTION</span></span>|<span data-ttu-id="fee37-479">String</span><span class="sxs-lookup"><span data-stu-id="fee37-479">String</span></span>|  
|<span data-ttu-id="fee37-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fee37-480">DATE_CREATED</span></span>|<span data-ttu-id="fee37-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-481">DateTime</span></span>|  
|<span data-ttu-id="fee37-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fee37-482">DATE_MODIFIED</span></span>|<span data-ttu-id="fee37-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="fee37-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="fee37-484">Indexes</span></span>  
  
|<span data-ttu-id="fee37-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-485">ColumnName</span></span>|<span data-ttu-id="fee37-486">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-487">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-488">String</span><span class="sxs-lookup"><span data-stu-id="fee37-488">String</span></span>|  
|<span data-ttu-id="fee37-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-490">String</span><span class="sxs-lookup"><span data-stu-id="fee37-490">String</span></span>|  
|<span data-ttu-id="fee37-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-491">TABLE_NAME</span></span>|<span data-ttu-id="fee37-492">String</span><span class="sxs-lookup"><span data-stu-id="fee37-492">String</span></span>|  
|<span data-ttu-id="fee37-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-493">INDEX_CATALOG</span></span>|<span data-ttu-id="fee37-494">String</span><span class="sxs-lookup"><span data-stu-id="fee37-494">String</span></span>|  
|<span data-ttu-id="fee37-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="fee37-496">String</span><span class="sxs-lookup"><span data-stu-id="fee37-496">String</span></span>|  
|<span data-ttu-id="fee37-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-497">INDEX_NAME</span></span>|<span data-ttu-id="fee37-498">String</span><span class="sxs-lookup"><span data-stu-id="fee37-498">String</span></span>|  
|<span data-ttu-id="fee37-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="fee37-499">PRIMARY_KEY</span></span>|<span data-ttu-id="fee37-500">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-500">Boolean</span></span>|  
|<span data-ttu-id="fee37-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="fee37-501">UNIQUE</span></span>|<span data-ttu-id="fee37-502">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-502">Boolean</span></span>|  
|<span data-ttu-id="fee37-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="fee37-503">CLUSTERED</span></span>|<span data-ttu-id="fee37-504">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-504">Boolean</span></span>|  
|<span data-ttu-id="fee37-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-505">TYPE</span></span>|<span data-ttu-id="fee37-506">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-506">Int32</span></span>|  
|<span data-ttu-id="fee37-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="fee37-507">FILL_FACTOR</span></span>|<span data-ttu-id="fee37-508">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-508">Int32</span></span>|  
|<span data-ttu-id="fee37-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="fee37-509">INITIAL_SIZE</span></span>|<span data-ttu-id="fee37-510">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-510">Int32</span></span>|  
|<span data-ttu-id="fee37-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="fee37-511">NULLS</span></span>|<span data-ttu-id="fee37-512">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-512">Int32</span></span>|  
|<span data-ttu-id="fee37-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="fee37-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="fee37-514">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-514">Boolean</span></span>|  
|<span data-ttu-id="fee37-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="fee37-515">AUTO_UPDATE</span></span>|<span data-ttu-id="fee37-516">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-516">Boolean</span></span>|  
|<span data-ttu-id="fee37-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="fee37-517">NULL_COLLATION</span></span>|<span data-ttu-id="fee37-518">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-518">Int32</span></span>|  
|<span data-ttu-id="fee37-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fee37-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="fee37-520">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-520">Int64</span></span>|  
|<span data-ttu-id="fee37-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-521">COLUMN_NAME</span></span>|<span data-ttu-id="fee37-522">String</span><span class="sxs-lookup"><span data-stu-id="fee37-522">String</span></span>|  
|<span data-ttu-id="fee37-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-523">COLUMN_GUID</span></span>|<span data-ttu-id="fee37-524">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-524">Guid</span></span>|  
|<span data-ttu-id="fee37-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-525">COLUMN_PROPID</span></span>|<span data-ttu-id="fee37-526">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-526">Int64</span></span>|  
|<span data-ttu-id="fee37-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="fee37-527">COLLATION</span></span>|<span data-ttu-id="fee37-528">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-528">Int16</span></span>|  
|<span data-ttu-id="fee37-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="fee37-529">CARDINALITY</span></span>|<span data-ttu-id="fee37-530">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="fee37-530">Decimal</span></span>|  
|<span data-ttu-id="fee37-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="fee37-531">PAGES</span></span>|<span data-ttu-id="fee37-532">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-532">Int32</span></span>|  
|<span data-ttu-id="fee37-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="fee37-533">FILTER_CONDITION</span></span>|<span data-ttu-id="fee37-534">String</span><span class="sxs-lookup"><span data-stu-id="fee37-534">String</span></span>|  
|<span data-ttu-id="fee37-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="fee37-535">INTEGRATED</span></span>|<span data-ttu-id="fee37-536">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="fee37-537">Microsoft Jet OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="fee37-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="fee37-538">Microsoft Jet OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fee37-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="fee37-539">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="fee37-539">Tables</span></span>  
  
- <span data-ttu-id="fee37-540">列</span><span class="sxs-lookup"><span data-stu-id="fee37-540">Columns</span></span>  
  
- <span data-ttu-id="fee37-541">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fee37-541">Procedures</span></span>  
  
- <span data-ttu-id="fee37-542">Views</span><span class="sxs-lookup"><span data-stu-id="fee37-542">Views</span></span>  
  
- <span data-ttu-id="fee37-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="fee37-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="fee37-544">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="fee37-544">Tables</span></span>  
  
|<span data-ttu-id="fee37-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-545">ColumnName</span></span>|<span data-ttu-id="fee37-546">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-547">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-548">String</span><span class="sxs-lookup"><span data-stu-id="fee37-548">String</span></span>|  
|<span data-ttu-id="fee37-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-550">String</span><span class="sxs-lookup"><span data-stu-id="fee37-550">String</span></span>|  
|<span data-ttu-id="fee37-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-551">TABLE_NAME</span></span>|<span data-ttu-id="fee37-552">String</span><span class="sxs-lookup"><span data-stu-id="fee37-552">String</span></span>|  
|<span data-ttu-id="fee37-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-553">TABLE_TYPE</span></span>|<span data-ttu-id="fee37-554">String</span><span class="sxs-lookup"><span data-stu-id="fee37-554">String</span></span>|  
|<span data-ttu-id="fee37-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-555">TABLE_GUID</span></span>|<span data-ttu-id="fee37-556">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-556">Guid</span></span>|  
|<span data-ttu-id="fee37-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-557">DESCRIPTION</span></span>|<span data-ttu-id="fee37-558">String</span><span class="sxs-lookup"><span data-stu-id="fee37-558">String</span></span>|  
|<span data-ttu-id="fee37-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-559">TABLE_PROPID</span></span>|<span data-ttu-id="fee37-560">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-560">Int64</span></span>|  
|<span data-ttu-id="fee37-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fee37-561">DATE_CREATED</span></span>|<span data-ttu-id="fee37-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-562">DateTime</span></span>|  
|<span data-ttu-id="fee37-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fee37-563">DATE_MODIFIED</span></span>|<span data-ttu-id="fee37-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fee37-565">列</span><span class="sxs-lookup"><span data-stu-id="fee37-565">Columns</span></span>  
  
|<span data-ttu-id="fee37-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-566">ColumnName</span></span>|<span data-ttu-id="fee37-567">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-568">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-569">String</span><span class="sxs-lookup"><span data-stu-id="fee37-569">String</span></span>|  
|<span data-ttu-id="fee37-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-571">String</span><span class="sxs-lookup"><span data-stu-id="fee37-571">String</span></span>|  
|<span data-ttu-id="fee37-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-572">TABLE_NAME</span></span>|<span data-ttu-id="fee37-573">String</span><span class="sxs-lookup"><span data-stu-id="fee37-573">String</span></span>|  
|<span data-ttu-id="fee37-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-574">COLUMN_NAME</span></span>|<span data-ttu-id="fee37-575">String</span><span class="sxs-lookup"><span data-stu-id="fee37-575">String</span></span>|  
|<span data-ttu-id="fee37-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-576">COLUMN_GUID</span></span>|<span data-ttu-id="fee37-577">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-577">Guid</span></span>|  
|<span data-ttu-id="fee37-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-578">COLUMN_PROPID</span></span>|<span data-ttu-id="fee37-579">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-579">Int64</span></span>|  
|<span data-ttu-id="fee37-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fee37-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="fee37-581">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-581">Int64</span></span>|  
|<span data-ttu-id="fee37-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="fee37-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="fee37-583">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-583">Boolean</span></span>|  
|<span data-ttu-id="fee37-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fee37-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="fee37-585">String</span><span class="sxs-lookup"><span data-stu-id="fee37-585">String</span></span>|  
|<span data-ttu-id="fee37-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fee37-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="fee37-587">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-587">Int64</span></span>|  
|<span data-ttu-id="fee37-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fee37-588">IS_NULLABLE</span></span>|<span data-ttu-id="fee37-589">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-589">Boolean</span></span>|  
|<span data-ttu-id="fee37-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-590">DATA_TYPE</span></span>|<span data-ttu-id="fee37-591">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-591">Int32</span></span>|  
|<span data-ttu-id="fee37-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-592">TYPE_GUID</span></span>|<span data-ttu-id="fee37-593">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-593">Guid</span></span>|  
|<span data-ttu-id="fee37-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fee37-595">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-595">Int64</span></span>|  
|<span data-ttu-id="fee37-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fee37-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fee37-597">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-597">Int64</span></span>|  
|<span data-ttu-id="fee37-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fee37-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fee37-599">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-599">Int32</span></span>|  
|<span data-ttu-id="fee37-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fee37-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="fee37-601">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-601">Int16</span></span>|  
|<span data-ttu-id="fee37-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fee37-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="fee37-603">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-603">Int64</span></span>|  
|<span data-ttu-id="fee37-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="fee37-605">String</span><span class="sxs-lookup"><span data-stu-id="fee37-605">String</span></span>|  
|<span data-ttu-id="fee37-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="fee37-607">String</span><span class="sxs-lookup"><span data-stu-id="fee37-607">String</span></span>|  
|<span data-ttu-id="fee37-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="fee37-609">String</span><span class="sxs-lookup"><span data-stu-id="fee37-609">String</span></span>|  
|<span data-ttu-id="fee37-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="fee37-611">String</span><span class="sxs-lookup"><span data-stu-id="fee37-611">String</span></span>|  
|<span data-ttu-id="fee37-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="fee37-613">String</span><span class="sxs-lookup"><span data-stu-id="fee37-613">String</span></span>|  
|<span data-ttu-id="fee37-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-614">COLLATION_NAME</span></span>|<span data-ttu-id="fee37-615">String</span><span class="sxs-lookup"><span data-stu-id="fee37-615">String</span></span>|  
|<span data-ttu-id="fee37-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="fee37-617">String</span><span class="sxs-lookup"><span data-stu-id="fee37-617">String</span></span>|  
|<span data-ttu-id="fee37-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="fee37-619">String</span><span class="sxs-lookup"><span data-stu-id="fee37-619">String</span></span>|  
|<span data-ttu-id="fee37-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-620">DOMAIN_NAME</span></span>|<span data-ttu-id="fee37-621">String</span><span class="sxs-lookup"><span data-stu-id="fee37-621">String</span></span>|  
|<span data-ttu-id="fee37-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-622">DESCRIPTION</span></span>|<span data-ttu-id="fee37-623">String</span><span class="sxs-lookup"><span data-stu-id="fee37-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fee37-624">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fee37-624">Procedures</span></span>  
  
|<span data-ttu-id="fee37-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-625">ColumnName</span></span>|<span data-ttu-id="fee37-626">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fee37-628">String</span><span class="sxs-lookup"><span data-stu-id="fee37-628">String</span></span>|  
|<span data-ttu-id="fee37-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fee37-630">String</span><span class="sxs-lookup"><span data-stu-id="fee37-630">String</span></span>|  
|<span data-ttu-id="fee37-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="fee37-632">String</span><span class="sxs-lookup"><span data-stu-id="fee37-632">String</span></span>|  
|<span data-ttu-id="fee37-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fee37-634">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-634">Int16</span></span>|  
|<span data-ttu-id="fee37-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fee37-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="fee37-636">String</span><span class="sxs-lookup"><span data-stu-id="fee37-636">String</span></span>|  
|<span data-ttu-id="fee37-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-637">DESCRIPTION</span></span>|<span data-ttu-id="fee37-638">String</span><span class="sxs-lookup"><span data-stu-id="fee37-638">String</span></span>|  
|<span data-ttu-id="fee37-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fee37-639">DATE_CREATED</span></span>|<span data-ttu-id="fee37-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-640">DateTime</span></span>|  
|<span data-ttu-id="fee37-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fee37-641">DATE_MODIFIED</span></span>|<span data-ttu-id="fee37-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="fee37-643">Views</span><span class="sxs-lookup"><span data-stu-id="fee37-643">Views</span></span>  
  
|<span data-ttu-id="fee37-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-644">ColumnName</span></span>|<span data-ttu-id="fee37-645">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-646">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-647">String</span><span class="sxs-lookup"><span data-stu-id="fee37-647">String</span></span>|  
|<span data-ttu-id="fee37-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-649">String</span><span class="sxs-lookup"><span data-stu-id="fee37-649">String</span></span>|  
|<span data-ttu-id="fee37-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-650">TABLE_NAME</span></span>|<span data-ttu-id="fee37-651">String</span><span class="sxs-lookup"><span data-stu-id="fee37-651">String</span></span>|  
|<span data-ttu-id="fee37-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fee37-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="fee37-653">String</span><span class="sxs-lookup"><span data-stu-id="fee37-653">String</span></span>|  
|<span data-ttu-id="fee37-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-654">CHECK_OPTION</span></span>|<span data-ttu-id="fee37-655">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-655">Boolean</span></span>|  
|<span data-ttu-id="fee37-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="fee37-656">IS_UPDATABLE</span></span>|<span data-ttu-id="fee37-657">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-657">Boolean</span></span>|  
|<span data-ttu-id="fee37-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fee37-658">DESCRIPTION</span></span>|<span data-ttu-id="fee37-659">String</span><span class="sxs-lookup"><span data-stu-id="fee37-659">String</span></span>|  
|<span data-ttu-id="fee37-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fee37-660">DATE_CREATED</span></span>|<span data-ttu-id="fee37-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-661">DateTime</span></span>|  
|<span data-ttu-id="fee37-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fee37-662">DATE_MODIFIED</span></span>|<span data-ttu-id="fee37-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="fee37-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="fee37-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="fee37-664">Indexes</span></span>  
  
|<span data-ttu-id="fee37-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fee37-665">ColumnName</span></span>|<span data-ttu-id="fee37-666">DataType</span><span class="sxs-lookup"><span data-stu-id="fee37-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fee37-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-667">TABLE_CATALOG</span></span>|<span data-ttu-id="fee37-668">String</span><span class="sxs-lookup"><span data-stu-id="fee37-668">String</span></span>|  
|<span data-ttu-id="fee37-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="fee37-670">String</span><span class="sxs-lookup"><span data-stu-id="fee37-670">String</span></span>|  
|<span data-ttu-id="fee37-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-671">TABLE_NAME</span></span>|<span data-ttu-id="fee37-672">String</span><span class="sxs-lookup"><span data-stu-id="fee37-672">String</span></span>|  
|<span data-ttu-id="fee37-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fee37-673">INDEX_CATALOG</span></span>|<span data-ttu-id="fee37-674">String</span><span class="sxs-lookup"><span data-stu-id="fee37-674">String</span></span>|  
|<span data-ttu-id="fee37-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fee37-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="fee37-676">String</span><span class="sxs-lookup"><span data-stu-id="fee37-676">String</span></span>|  
|<span data-ttu-id="fee37-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-677">INDEX_NAME</span></span>|<span data-ttu-id="fee37-678">String</span><span class="sxs-lookup"><span data-stu-id="fee37-678">String</span></span>|  
|<span data-ttu-id="fee37-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="fee37-679">PRIMARY_KEY</span></span>|<span data-ttu-id="fee37-680">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-680">Boolean</span></span>|  
|<span data-ttu-id="fee37-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="fee37-681">UNIQUE</span></span>|<span data-ttu-id="fee37-682">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-682">Boolean</span></span>|  
|<span data-ttu-id="fee37-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="fee37-683">CLUSTERED</span></span>|<span data-ttu-id="fee37-684">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-684">Boolean</span></span>|  
|<span data-ttu-id="fee37-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="fee37-685">TYPE</span></span>|<span data-ttu-id="fee37-686">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-686">Int32</span></span>|  
|<span data-ttu-id="fee37-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="fee37-687">FILL_FACTOR</span></span>|<span data-ttu-id="fee37-688">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-688">Int32</span></span>|  
|<span data-ttu-id="fee37-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="fee37-689">INITIAL_SIZE</span></span>|<span data-ttu-id="fee37-690">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-690">Int32</span></span>|  
|<span data-ttu-id="fee37-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="fee37-691">NULLS</span></span>|<span data-ttu-id="fee37-692">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-692">Int32</span></span>|  
|<span data-ttu-id="fee37-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="fee37-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="fee37-694">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-694">Boolean</span></span>|  
|<span data-ttu-id="fee37-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="fee37-695">AUTO_UPDATE</span></span>|<span data-ttu-id="fee37-696">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-696">Boolean</span></span>|  
|<span data-ttu-id="fee37-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="fee37-697">NULL_COLLATION</span></span>|<span data-ttu-id="fee37-698">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-698">Int32</span></span>|  
|<span data-ttu-id="fee37-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fee37-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="fee37-700">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-700">Int64</span></span>|  
|<span data-ttu-id="fee37-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fee37-701">COLUMN_NAME</span></span>|<span data-ttu-id="fee37-702">String</span><span class="sxs-lookup"><span data-stu-id="fee37-702">String</span></span>|  
|<span data-ttu-id="fee37-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-703">COLUMN_GUID</span></span>|<span data-ttu-id="fee37-704">GUID</span><span class="sxs-lookup"><span data-stu-id="fee37-704">Guid</span></span>|  
|<span data-ttu-id="fee37-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fee37-705">COLUMN_PROPID</span></span>|<span data-ttu-id="fee37-706">Int64</span><span class="sxs-lookup"><span data-stu-id="fee37-706">Int64</span></span>|  
|<span data-ttu-id="fee37-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="fee37-707">COLLATION</span></span>|<span data-ttu-id="fee37-708">Int16</span><span class="sxs-lookup"><span data-stu-id="fee37-708">Int16</span></span>|  
|<span data-ttu-id="fee37-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="fee37-709">CARDINALITY</span></span>|<span data-ttu-id="fee37-710">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="fee37-710">Decimal</span></span>|  
|<span data-ttu-id="fee37-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="fee37-711">PAGES</span></span>|<span data-ttu-id="fee37-712">Int32</span><span class="sxs-lookup"><span data-stu-id="fee37-712">Int32</span></span>|  
|<span data-ttu-id="fee37-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="fee37-713">FILTER_CONDITION</span></span>|<span data-ttu-id="fee37-714">String</span><span class="sxs-lookup"><span data-stu-id="fee37-714">String</span></span>|  
|<span data-ttu-id="fee37-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="fee37-715">INTEGRATED</span></span>|<span data-ttu-id="fee37-716">ブール型</span><span class="sxs-lookup"><span data-stu-id="fee37-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fee37-717">関連項目</span><span class="sxs-lookup"><span data-stu-id="fee37-717">See also</span></span>

- [<span data-ttu-id="fee37-718">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="fee37-718">ADO.NET Overview</span></span>](ado-net-overview.md)
