# NAME

DBIx::Fixture::Admin - facilitate data management by the fixtures

# SYNOPSIS

    # in perl code
    use DBIx::Fixture::Admin;

    use DBI;
    my $dbh = DBI->connect("DBI:mysql:sample", "root", "");

    my $admin = DBIx::Fixture::Admin->new(
        +{
            fixture_path  => "./fixture/",
            driver        => "mysql",
            load_opt      => "update",
            dbh           => $dbh,
            ignore_tables => ["user_.*", ".*_log"]  # ignore management
        },
    );

    $admin->load_all(); # load all fixture
    $admin->create_all(); # create all fixture
    $admin->create(tables => ["sample"]); # create sample table fixture
    $admin->load(tables => ["sample"]); # load sample table fixture

    # in CLI
    # use config file .fixture in current dir
    # see also .fixture in thish repository
    create-fixture # execute create_all
    load-fixture   # execute load_all

# DESCRIPTION

DBIx::Fixture::Admin is facilitate data management by the fixtures

# LICENSE

Copyright (C) meru\_akimbo.

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# AUTHOR

meru\_akimbo <merukatoruayu0@gmail.com>
