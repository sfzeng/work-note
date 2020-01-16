## s3tests
github: https://github.com/ceph/s3-tests

### 用法
列出所有测试用例
```
./virtualenv/bin/nosetests --collect-only --verbosity=2 > testcases.txt 2>&1
```
执行用例
```
S3TEST_CONF=s3tests.conf ./virtualenv/bin/nosetests s3tests_boto3.functional.test_s3.test_bucket_list_many
```
